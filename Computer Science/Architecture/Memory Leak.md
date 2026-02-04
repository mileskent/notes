---
date: 2025-01-07
---
When you [[Heap Allocation|allocate memory]] without [[free|freeing]] it.
Example:
```
void foo (void) {
	char *ca = malloc(...);
	/* no free */
	return;
}
```
### See also
[[malloc]]