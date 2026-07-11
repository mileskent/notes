---
date: 2026-06-24
aliases:
  - PIMPL
---
The *Pointer to Implementation* (PIMPL) idiom in [[C++]] hides a class's private members behind a forward-declared implementation struct, accessed through a [[C++ Smart Pointer|std::unique_ptr]]. This keeps implementation details out of the header, reducing compile-time coupling.

# Example

```cpp
// database.h
class Database {
public:
    Database(const std::string& connection_string);
    ~Database();
    std::optional<Row> query(const std::string& sql) const;
private:
    struct Impl;
    std::unique_ptr<Impl> impl;
};

// database.cpp
#include <libpq.h>  // heavy dependency stays out of the header

struct Database::Impl {
    PGconn* conn;
    std::optional<Row> execute(const std::string& sql) const { /* ... */ }
};

Database::Database(const std::string& cs)
    : impl(std::make_unique<Impl>()) { /* ... */ }
Database::~Database() = default;

std::optional<Row> Database::query(const std::string& sql) const {
    return impl->execute(sql);
}
```


| Pros                                                                                   | Cons                                     |
| -------------------------------------------------------------------------------------- | ---------------------------------------- |
| Compilation Dependency Decoupling: changes to Impl do not force consumers to recompile | Pointer indirection on every method call |
| [[Application Binary Interface\|ABI]] stability: class is always one pointer wide      | Heap allocation for the Impl object      |
| Header cleanliness: class includes stay out of the public includes                     | Cannot be inlined across the boundary    |
