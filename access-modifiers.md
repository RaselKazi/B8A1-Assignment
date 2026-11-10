# Access Modifiers in TypeScript OOP

In TypeScript, Access modifiers control who can read or change the properties and methods of a class. “Access Modifiers.. Let's say you're in a school: some information is available to everyone, some is private, and some is shared only with family members.

TypeScript has four Access modifiers: `public`, `private`, `protected`, and `readonly`.
In this blog, I explain how each one works with simple examples.

## 1. Public – Can be accessed from anywhere

`public` allows a property or method to be accessed from both inside and outside the class. It is the default modifier

```ts
class Student {
  public name = "Rasel";
}

const student = new Student();

console.log(student.name); // Rasel
```

**Just like:** A school notice board that everyone can read.

## 2. Private – Accessible only inside the class

`private` allows a property or method to be accessed only within the class where they are defined. It cannot be accessed from outside the class.

```ts
class BankAccount {
  private balance = 1000;

  public showBalance() {
    return this.balance;
  }
}

const account = new BankAccount();

console.log(account.showBalance()); // 1000
// console.log(account.balance); // Error
```

**Just like:** Your own personal diary that only you can read.

## 3. Protected – Parent and Child Classes Can Access

`protected` works like `private`, but child classes can also access the property or method.

```ts
class Employee {
  protected name = "Rasel";
}

class Manager extends Employee {
  showName() {
    return this.name;
  }
}

const manager = new Manager();

console.log(manager.showName()); // Rasel
// console.log(manager.name); // Error
```

**Just like:** A family secret parents can share with their children, but not others.

## 4. Readonly – Cannot be changed

`readonly` allows a property to be read but its value cannot be changed after initialization.

```ts
class User {
  readonly id = 101;
}

const user = new User();

console.log(user.id); // 101
// user.id = 202; // Error
```

**Just like:** A school registration number that cannot be changed.

## Quick Comparison

| Modifier    | Inside Class | Child Class | Outside Class          |
| ----------- | ------------ | ----------- | ---------------------- |
| `public`    | Yes          | Yes         | Yes                    |
| `private`   | Yes          | No          | No                     |
| `protected` | Yes          | Yes         | No                     |
| `readonly`  | Readable     | Readable    | Readable, not writable |

**Note:** `readonly` controls reassignment, not access. It can be combined with `public`, `private`, or `protected`.

## Conclusion

- `public`: Accessible from anywhere.
- `private`: Accessible only within the declaring class.
- `protected`: Accessible within the declaring class and its subclasses.
- `readonly`: Prevents a property from being reassigned after initialization.

Access modifiers help control how class members are used, making code easier to understand,cleaner, and easier to maintain.
