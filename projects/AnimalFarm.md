---
layout: project
type: project
image: 
title: "Animal Farm"
date: 2022
published: true
labels:
  - C
  - C++
  - Object-oriented programming
  - Linked List
summary: "A project to show proficiency in C++ and in Object-oriented programming"
---

# Animal Farm Project

Animal Farm is a C++ project that demonstrates advanced object-oriented programming concepts through the implementation of a virtual animal management system. The application showcases the use of inheritance, polymorphism, and data structures, particularly focusing on a custom implementation of a singly linked list.

As the sole developer, I was responsible for designing and implementing the entire system. I began by creating a robust class hierarchy for different animal types, starting with a base `Animal` class and extending it to create more specific classes like `Mammal` and `Cat`. I then developed a custom `SinglyLinkedList` class to efficiently manage and store the animal objects.

Key features of the Animal Farm project include:

1. Extensible animal hierarchy: The project allows for easy addition of new animal types through inheritance.
2. Custom data structure: A singly linked list implementation provides efficient storage and retrieval of animal objects.
3. Weight management: A `Weight` class handles various weight units and conversions (pounds, kilograms, slugs).
4. Error handling and validation: Extensive error checking ensures data integrity throughout the system.

Here's a code snippet that illustrates how we add animals to our custom linked list and interact with them:

```cpp
SinglyLinkedList catDB;
catDB.push_front(new Cat("Loki", Color::CREAM, true, Gender::MALE, 1.0));
catDB.push_front(new Cat("Milo", Color::BLACK, true, Gender::MALE, 1.1));
catDB.push_front(new Cat("Bella", Color::BROWN, true, Gender::FEMALE, 1.2));

for(Animal* pAnimal = (Animal*)catDB.get_first(); pAnimal != nullptr; pAnimal = (Animal*)List::get_next((Node*)pAnimal)) {
    cout << pAnimal->speak() << endl;
}
```

This project not only demonstrates proficiency in C++ programming but also showcases understanding of important software engineering principles such as code organization, error handling, and creating reusable and extensible code structures.

For more information and to view the source code, check out the [GitHub repository](https://github.com/lyons811/ee205-animal-farm.-).
