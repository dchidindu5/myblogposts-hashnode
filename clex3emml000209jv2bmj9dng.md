---
title: "Approaches to Writing Memory Safe C++"
seoTitle: "Writing memory safe......"
seoDescription: "Memory management refers to the process of managing computer memory, including allocating and de-allocating memory for programs and data structures......."
datePublished: Mon Mar 06 2023 17:25:03 GMT+0000 (Coordinated Universal Time)
cuid: clex3emml000209jv2bmj9dng
slug: approaches-to-writing-memory-safe-c
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678122852817/d617f7d6-5734-4b5c-8abe-9a12a164bc9f.png
tags: cpp, operating-system, opensource, os, memory-management

---

Understanding memory management is a crucial skill for C++ programmers to ensure their programs run efficiently and reliably. Lately, there has been a chant by some big tech industries to use memory-safe programming languages. The recommendation has spurred conversations about what programming languages to use to develop high-performance software and given Rust - developers added more fuel to chant that Rust is the future.

Memory management refers to the process of managing computer memory, including allocating and deallocating memory for programs and data structures. In C++, memory management is an important topic as it allows programmers to efficiently use memory resources and avoid common pitfalls such as memory leaks and segmentation faults.

To effectively manage memory in C++, developers must implement the practice of modern C++ techniques to improve memory safety. Let’s examine a few C++ techniques that can help developers improve memory safety. These are not complete list, but they are examples of how C++ shouldn’t just be tossed aside for a new kid on the block.

> N/B The following approaches are just a few examples, but there are many more.


### Approach #1

Use smart pointers:

Raw pointers are low-level constructs that can be easily misused, leading to memory bugs. Instead, use smart pointers, references, or other higher-level abstractions where possible. Smart pointers are objects that wrap dynamically allocated objects and manage their lifetimes automatically, thus avoiding memory leaks and freeing up resources.

Within modern C++, developers can leverage smart pointers, which includes:

* `unique_ptr`
    
* `shared_ptr`
    
* `weak_ptr`
    

Let’s define the listed smart pointer approaches, `unique_ptr` is unique in the sense that it cannot be copied or shared, only one `unique_ptr` can own the object at any given time until it is deallocated. Using a raw pointer does not guarantee this behaviour which can result in memory leaks.

`shared_ptr` implements shared ownership. Any number of these smart pointers jointly own the object. The owned object gets destroyed upon destroying the last owning smart pointer.

`weak_ptr` tracks the lifetime of an object managed by `shared_ptr` without affecting its lifetime. It does not have ownership of the object it points to. It is required to observe an object’s lifetime without extending it.

```cpp
#include <memory>
#include <iostream>

int main()
{
  // Use make_unique to create a unique_ptr to a dynamically allocated int
  auto ptr = std::make_unique<int>(42);
 
  // Access the value stored in the unique_ptr
  std::cout << *ptr << std::endl;
 
  // The unique_ptr is automatically freed when it goes out of scope
  return 0;
}
```

In the snippet above, `std::make_unique_ptr` is used to create a `std::unique_ptr` to a dynamically allocated int. The unique\_ptr manages the lifetime of the int, freeing it automatically when it goes out of scope.

The `unique_ptr` takes ownership of the memory and automatically frees it when the `unique_ptr` goes out of scope. This ensures that there are no memory leaks or dangling pointers. We can also access the integer using the dereference operator `*`.  

### Approach #2

RAII (Resource Acquisition Is Initialization):

RAII works by defining a class that encapsulates a resource and using that class to automatically manage the lifetime of the resource. When an object of a class is created, the resource is acquired, and when the object is destroyed, the resource is released. This ensures that a resource is always in check to see when it is properly acquired and released regardless of any exceptions during the lifetime of the object. This means that the resource is automatically managed by the object’s lifecycle, and the programmer does not need to worry about releasing the resource manually. RAII is implemented using constructors and destructors of C++ classes.

This technique involves tying the lifetime of a resource to the lifetime of an object. The resource is acquired when the object is constructed, and released when the object is destroyed.

Snippet of a RAII technique being used [https://godbolt.org/z/qx34G33nj](https://godbolt.org/z/qx34G33nj)


### Approach #3

Using the C++ Standard Library

The C++ Standard Library provides many useful containers and algorithms that simplify the task of managing dynamically allocated objects. For example, using `std::vector` instead of raw arrays reduces the risk of memory bugs.

## Other Techniques to Consider

* Implementing custom destructors: When defining custom classes that manage dynamically allocated memory, it is important to implement a proper destructor to ensure that memory is freed when the object is no longer needed, like the Rule of Zero, Rule of Five, and Rule of Three.
    
* Writing unit tests: Unit tests can help you catch memory bugs early in the development process before they cause problems in production.
    
* Avoiding `new` and `delete`: Allocating and deallocating memory dynamically can be error-prone. Instead, use `std::make_unique` or `std::make_shared` to create smart pointers, or rely on stack-allocated objects and move semantics.
    
* Use of static analysis tools to find memory leaks, threading issues, bugs, and other potential issues. Again, many static analysis tools are out there, like clang, cppcheck, valgrind, and other commercial tools.
    
* Finally, keep an eye on the changes made to the C++ standards. C++ is updated every three years. The language is evolving, and new tools are constantly added. Security and memory safety are essential, and we’ll likely see many improvements in the language to that respect in the future.
    

### Conclusion

C++ is a powerful and feature-filled language, unfortunately, it is not a memory-safe language but with different techniques and methodologies, safety can be achieved. Ultimately, whether you use a memory-safe language or not, the developer needs to think through what they are doing and how it affects memory.

## Sources

* [Understanding Smart Pointers in C++](https://betterprogramming.pub/smart-pointers-in-cpp-708486276526)  
    
* [Dynamic Memory Management](https://en.cppreference.com/w/cpp/memory)  
    
* [Five techniques for writing memory safe C++](https://www.embedded.com/5-techniques-for-writing-memory-safe-c/)