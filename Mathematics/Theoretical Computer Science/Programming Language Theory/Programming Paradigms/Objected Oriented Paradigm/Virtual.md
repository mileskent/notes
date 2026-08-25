In [[Object Oriented Programming Language|OOP]], [[Virtual Function|virtual functions]], denoted by the "virtual" keyword, enable [[Dynamic Dispatch]] at [[Runtime]], and enable overriding the marked function in child classes. 

# Tracing End-to-End
We are going to examine the following snippet.

```cpp
Animal *ptr = new Dog();
ptr->speak();
```

Suppose we have a parent class *Animal* and several child classes, including *Dog*. *Animal* has some virtual function called speak. It could be pure virtual or not. If it was pure virtual, this would make the parent class abstract and prevent it from being instantiated as a value (i.e. point to abstract class still okay). *Dog* overrides the virtual speak function. 

```cpp
class Animal {
private: 
	std::string name;
public:
	virtual void speak() = 0; // Pure virtual
	/* OR */
	virtual void speak() { ... }; // Implemented
}

class Dog : public Animal {
	void speak() override { ... };
}
```

Once you add at least one virtual keyword to any class, it (and its children via inheritance) receives a hidden private member variable called [[vptr]] which is a pointer to the [[vtable]]. Consequently, every class with virtual functions that a child class inherits from increases the size of that child class, as a result of needing to store those vptrs. Generally a class only has one or zero vptrs unless you do multiple inheritance.

If a class inherits from multiple parent classes that impart their vtables to the child class, the child receives a vptr for each class it inherits, just as it would inherit any other member variable. 

Specifically, a pointer to an array of function pointers where the functions return void. The functions don't actually have to return void, but they are cast that way to conform to the array.  

```cpp
class Animal {
private:
	std::string name;
	void (**__vptr)(); // Hidden
}
class Dog {
	/* 
	inherits:
	std::string name;
	void (**__vptr)();
	*/
}
```

The vtable stores function pointers and also some metadata at the beginning, kind of like how [[malloc]] stores metadata. 

If a parent class has a certain array of its own function pointers by default in its vtable. The child class is given an identical vtable at compile time, however the compiler overwrites all the functions that the child overrides with function pointers to the child implementation. The assignment of the child's vptr to this static data segment vtable is added by the compiler as a hidden section at the top of the constructor, just like how it adds the vptr secretly.

Now back to the snippet. 

```cpp
Animal *ptr = new Dog();
ptr->speak();
```

* At compile time, Animal's vtable is created and it is given a vptr. Dog inherits animal's vptr member variable. Animal's hidden preconstructor is written to assign its vptr to its static vtable. Dog's hidden preconstructor is written to assign its vptr to its static vtable, which is copied from Animal's with all the entries corresponding to what Dog overrode being overwritten with the new function pointers.
* At runtime, on line one, Animal's constructor is not called on the left hand side, as we only declare an Animal pointer. First the memory for a Dog is dynamically allocated onto the heap. Then, Dog's constructor is called, it calls Animal's constructor now, which assigns the vptr to Animal's static vtable. Then it runs through Dog's hidden preconstructor to assign the vptr and then the rest of Dog's constructor. After construction, we store a reference to this memory blob in the Animal pointer.
* At runtime, on line two, we dereference the Animal pointer to call its virtual speak function, which goes through the vptr to the index corresponding to speak in the vtable, and calls that function via its function pointer. Two pointer dereferences occur. 
* Then we call the dynamically dispatched Dog::speak

# What Happens without Virtual?
Without marking the parent class's function virtual, if the child class implements a function of the same name, it shadows the parent and prevents the child class from being able to access the parent's version: called "name hiding". When calling the overriden child function by value, you calling it directly. When calling via the parent pointer, you get static dispatch, and the function collision  is resolved from the type of the pointer, which is an Animal, so the parent function is called. Both of the above are resolved at compile time.
