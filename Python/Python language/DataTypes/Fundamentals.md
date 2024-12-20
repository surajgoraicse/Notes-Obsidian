#### Mutable vs Immutable
| Feature               | Mutable                                               | Immutable                                                           |
| --------------------- | ----------------------------------------------------- | ------------------------------------------------------------------- |
| **Modifiability**     | Can be changed after creation.                        | Cannot be changed after creation.                                   |
| **Examples**          | Lists, Dictionaries, Sets                             | Strings, Tuples, Numbers, Frozen Sets                               |
| **Memory Efficiency** | Modifications happen in-place.                        | New objects are created for changes.                                |
| **Hashability**       | Typically unhashable (not usable as dictionary keys). | Hashable (usable as dictionary keys) if all elements are immutable. |
| **Performance**       | May have performance overhead for locking mechanisms. | Generally faster for read-only operations.                          |
