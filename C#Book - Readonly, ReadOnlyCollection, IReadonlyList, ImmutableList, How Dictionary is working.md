init (Introduced in C# 9): -> set a property only during object initialization, Once the object is constructed, the property becomes immutable.
public string Name { get; init; }
private set: -> property can be modified only within the class itself and not from outside the class.
public decimal Balance { get; private set; }
No Set (Read-Only Properties): -> The value can only be assigned during initialization or within the constructor of the class.
public double Radius { get; }
readonly (For Fields): -> used for fields in a class or struct. It ensures the field can be assigned only once, either at declaration or in the constructor.

![Image](https://github.com/user-attachments/assets/b40cf00e-9efb-448d-a6b6-7b31cb1afc40)

1.. Readonly PropertiesA readonly property can only be assigned a value during its declaration or in the constructor of the class. After that, its value cannot be changed, but you can read it.
2. Readonly ListA readonly list means that the reference to the list cannot be changed (you can’t assign a new list to it), but the elements inside the list can still be modified.3. Readonly DictionarySimilar to a readonly List, a readonly dictionary prevents reassignment of the dictionary itself, but its contents (keys and values) can be modified.4. Readonly FieldsFields can also be marked readonly, which means they can only be assigned a value during declaration or in the constructor.
MyClass obj = new MyClass(new List<int> { 1, 2, 3 });
obj.MyList.Add(4); // This is allowed, modifying the list's contents.
obj.MyList = new List<int>(); // This will result in a compile-time error because MyList is readonly.

Readonly Property: The value can only be assigned once, either during initialization or in a constructor.
Readonly List/Dictionary: The reference to the collection cannot be changed after construction, but you can modify its contents (add/remove items).
Readonly Field: A field that can only be set during declaration or in the constructor and cannot be reassigned later.
ReadOnlyCollection: Provides a read-only wrapper around an existing collection (like a List<T>), preventing modifications through the wrapper but allowing changes to the underlying collection if accessed directly.
Readonly List: A list field or variable that is marked with readonly, which prevents reassignment of the reference to a new list, but allows modification of the list's contents (e.g., adding or removing elements).
ReadOnlyDictionary: A read-only wrapper for a Dictionary<TKey, TValue> that prevents any modifications to the dictionary, ensuring its contents are not changed.
Readonly Dictionary: A dictionary field or variable marked with readonly, which prevents reassignment of the reference to a new dictionary, but still allows modification of the dictionary's contents (e.g., adding or removing key-value pairs).

IReadOnlyList<T> and ImmutableList<T>
IReadOnlyList<T> - Provides read-only access (no modifications) to a collection.

Mutable vs Immutable
A mutable object is an object whose state (its data/values) can be changed after it is created.
An immutable object is an object whose state cannot be changed after it has been created. Thread-safe because multiple threads can read an immutable object without worrying about modifications

![Image](https://github.com/user-attachments/assets/ba1ccd48-6011-4bdc-94d7-4d63c4f7acfb)

https://dev.to/wirefuture/exploring-the-internals-of-dictionary-in-c-1i5p#:~:text=This%20article%20will%20demonstrate%20how%20dictionaries%20work%20in,the%20ability%20to%20quickly%20find%20values%20by%20key.

How Dictionaries Work
Array of Buckets - Each bucket can hold multiple entries when collisions. 
Each entry consists of:
hashCode: The computed hash code of the key.
next: The index of the next entry in case of a collision.
key: The actual key.
value: The associated value.

If no collision occurs, the entry is stored at that index.
If a collision occurs (another key hashes to the same index), chaining is used:
The new entry is linked to the existing one via the next pointer.

Collision Handling
Uses chaining (linked list within buckets).
If multiple keys hash to the same bucket, they are stored as a linked list.

ReadOnlyCollection<T> in C#
C# provides a read-only wrapper around an existing collection. It ensures that the collection cannot be modified (e.g., adding, removing, or replacing elements) while still allowing read access.

![Image](https://github.com/user-attachments/assets/1a9076ac-61b7-4b76-bfdb-a3799fc8d521)

![Image](https://github.com/user-attachments/assets/639f749c-9f94-484a-90e1-0edd349a3ae8)

![Image](https://github.com/user-attachments/assets/6fa1ae11-331e-47d7-8f68-c58d9e141a60)


Mutable vs Immutable:
Mutable Objects
Definition: Mutable objects can be changed after they are created. This means you can modify, add, or remove elements or attributes without creating a new object.
Examples:
In Python: Lists, dictionaries, sets.
In Java: StringBuilder, arrays.
Advantages:
Can save memory by modifying the same object instead of creating new ones.
Useful for cases where frequent changes are required.

Immutable Objects
Definition: Immutable objects cannot be changed after they are created. Any modification results in the creation of a new object.
Examples:
In Python: Strings, tuples, integers, floats.
In Java: Strings, primitive wrappers like Integer, Double.
Advantages:
Safer to use in multi-threaded environments because they prevent unintended side effects.
Predictable and easier to debug.
