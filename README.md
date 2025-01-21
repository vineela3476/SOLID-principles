The SOLID principles are a set of five design principles that aim to make software designs more understandable, flexible, and maintainable. These principles were introduced by Robert C. Martin (Uncle Bob) and are widely used in object-oriented programming.

## SOLID Principles Overview
### S - Single Responsibility Principle (SRP)
A class should have only one reason to change.

Each class should have a single responsibility or job.
This reduces the complexity of the class and makes it easier to maintain and test.
Example:
Instead of a single Report class handling both report generation and database operations, split it into ReportGenerator and ReportSaver.

``` cpp
#include <iostream>
#include <string>

// Class for baking bread
class BreadBaker {
public:
    void bakeBread() {
        std::cout << "Baking high-quality bread..." << std::endl;
    }
};

// Class for managing inventory
class InventoryManager {
public:
    void manageInventory() {
        std::cout << "Managing inventory..." << std::endl;
    }
};

// Class for ordering supplies
class SupplyOrder {
public:
    void orderSupplies() {
        std::cout << "Ordering supplies..." << std::endl;
    }
};

// Class for serving customers
class CustomerService {
public:
    void serveCustomer() {
        std::cout << "Serving customers..." << std::endl;
    }
};

// Class for cleaning the bakery
class BakeryCleaner {
public:
    void cleanBakery() {
        std::cout << "Cleaning the bakery..." << std::endl;
    }
};

int main() {
    BreadBaker baker;
    InventoryManager inventoryManager;
    SupplyOrder supplyOrder;
    CustomerService customerService;
    BakeryCleaner cleaner;

    // Each class focuses on its specific responsibility
    baker.bakeBread();
    inventoryManager.manageInventory();
    supplyOrder.orderSupplies();
    customerService.serveCustomer();
    cleaner.cleanBakery();

    return 0;
}
```

### O - Open/Closed Principle (OCP)
Software entities (classes, modules, functions) should be open for extension but closed for modification.

You should be able to add new functionality to a class without altering its existing code.
Example:
Use interfaces or inheritance to add new features rather than modifying the original class.

### L - Liskov Substitution Principle (LSP)
Subtypes must be substitutable for their base types.

Objects of a superclass should be replaceable with objects of a subclass without altering the correctness of the program.
Example:
If a Bird class has a Fly() method, a subclass Penguin should not override it since penguins can’t fly. Instead, restructure the design to avoid inappropriate inheritance.

### I - Interface Segregation Principle (ISP)
A class should not be forced to implement interfaces it does not use.

Break large interfaces into smaller, more specific ones.
Example:
Instead of a single Animal interface with methods like Fly() and Swim(), create specific interfaces like IFlyable and ISwimmable.

### D - Dependency Inversion Principle (DIP)
Depend on abstractions, not on concrete implementations.

High-level modules should not depend on low-level modules. Both should depend on abstractions (interfaces).
Example:
Instead of a Car class directly creating an instance of Engine, inject an IEngine interface into the Car class.