# Access Modifiers in TypeScript OOP

Access modifiers control who can access a class's properties and methods. Think of a school: some information is available to everyone, some is private, and some is shared only with family members.

TypeScript has four important keywords: `public`, `private`, `protected`, and `readonly`.

## 1. Public – Everyone Can Access

`public` allows a property or method to be accessed from both inside and outside the class.

```ts
class Student {
  public name = "Rasel";
}

const student = new Student();

console.log(student.name); // Rasel
```

**Think of it like:** A school notice board that everyone can read.

## 2. Private – Only the Same Class Can Access

`private` allows a property or method to be accessed only within the class where it is declared.

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

**Think of it like:** A personal diary that only you can read.

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

**Think of it like:** A family secret that parents can share with their children, but not with outsiders.

## 4. Readonly – Cannot Be Reassigned

`readonly` allows a property to be read but prevents it from being reassigned after initialization.

```ts
class User {
  readonly id = 101;
}

const user = new User();

console.log(user.id); // 101
// user.id = 202; // Error
```

**Think of it like:** A school registration number that cannot be changed.

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

Access modifiers help control how class members are used, making code easier to understand and maintain.
