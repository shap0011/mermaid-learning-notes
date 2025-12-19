# Class Diagram

---

## Mermaid.js - Class Diagram

- A class diagram is a graphical representation of classes and their relationships in a system. It's a fundamental tool in object-oriented modeling,providing a visual overview of the system's structure and how objects interact with each other.
- It describes the structure of a system by showing the system's classes, their attributes, operations (or methods), and the relationships among objects.
- In a class diagram, classes are represented as rectangles, and the relationships between them are depicted by connecting lines.

---

## Defining a Class Diagram

````
```mermaid
classDiagram
    class BankAccount{
        owner
        balance
        withdrawal()
        deposit()
    }
    class Person
        Person: name
        Person: age
        Person: walk()
        Person: talk()
```
````

```mermaid
classDiagram
    class BankAccount{
        owner
        balance
        withdrawal()
        deposit()
    }
    class Person
        Person: name
        Person: age
        Person: walk()
        Person: talk()
```

---

## Class Visibility and Types

\+ public, accessible to all xml classes
\- private, not accessible to all other classes but itself
\# protected
\~ the class is accessible only for packages which are inherits \* abstract method
\$ static method

````
```mermaid
classDiagram
    class BankAccount{
        -String owner
        -BigDecimal balance
        +withdrawal(amount) bool
        +deposit(amount) int

        method1()*
        method2() String$
    }
    class Person
        Person: -String name
        Person: -Integer age
        Person: #List~string~ siblings
        Person: +walk(Integer distance)
        Person: +talk() List~string~
```
````

```mermaid
classDiagram
    class BankAccount{
        -String owner
        -BigDecimal balance
        +withdrawal(amount) bool
        +deposit(amount) int

        method1()*
        method2() String$
    }
    class Person
        Person: -String name
        Person: -Integer age
        Person: #List~string~ siblings
        Person: +walk(Integer distance)
        Person: +talk() List~string~
```

---

## Class relationship

|  Type   |  Description  |
| :-----: | :-----------: |
| `<\|--` |  Inheritance  |
|  `*--`  |  Composition  |
|  `o--`  |  Aggregation  |
|  `-->`  |  Association  |
|  `--`   | Link (Solid)  |
|  `..>`  |  Dependency   |
| `..\|>` |  Realization  |
|  `..`   | Link (dashed) |

````
```mermaid
classDiagram
    class BankAccount{
        -String owner
        -BigDecimal balance
        +withdrawal(amount) bool
        +deposit(amount) int

        method1()*
        method2() String$
    }
    class Person
        Person: -String name
        Person: -Integer age
        Person: #List~string~ siblings
        Person: +walk(Integer distance)
        Person: +talk() List~string~

BankAccount<|--|>Person
```
````

```mermaid
classDiagram
    class BankAccount{
        -String owner
        -BigDecimal balance
        +withdrawal(amount) bool
        +deposit(amount) int

        method1()*
        method2() String$
    }
    class Person
        Person: -String name
        Person: -Integer age
        Person: #List~string~ siblings
        Person: +walk(Integer distance)
        Person: +talk() List~string~

BankAccount<|--|>Person
```

````
```mermaid
---
title: Animal Relationship
---
classDiagram
    class Animal {
        - age int
        + makeSound() void
    }

    class Mammal {
        # furColor string
        - giveBirth() void
    }

    class Reptile {
        # scaleType string
        + layEggs() void
    }

    class Dog {
        # breed string
        + bark() void
    }

    class Dolphin {
        + swim() void
    }

    class Platypus {
        # poisonous boolean
        + swim() void
    }

    Animal <|-- Mammal
    Animal <|-- Reptile
    Mammal o-- Dog
    Mammal *-- Dolphin
    Reptile *-- Platypus
```
````

```mermaid
---
title: Animal Relationship
---
classDiagram
    class Animal {
        - age int
        + makeSound() void
    }

    class Mammal {
        # furColor string
        - giveBirth() void
    }

    class Reptile {
        # scaleType string
        + layEggs() void
    }

    class Dog {
        # breed string
        + bark() void
    }

    class Dolphin {
        + swim() void
    }

    class Platypus {
        # poisonous boolean
        + swim() void
    }

    Animal <|-- Mammal
    Animal <|-- Reptile
    Mammal o-- Dog
    Mammal *-- Dolphin
    Reptile *-- Platypus

```
