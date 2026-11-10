# Access Modifiers in TypeScript OOP

In TypeScript access modifiers help control who can read or change the properties and methods of a class. Think of it like rules in a school: some things are open for everyone some are kept private. Some are shared only with close family.

TypeScript has four access modifiers: ` `private` `protected`and`readonly`. In this blog I’ll explain each one with examples.

## 1. Public – Can be accessed from anywhere

`public` means a property or method can be used both inside and outside the class. It is also the default modifier if you don’t specify one.

```ts
class Student {
  public name = "Rasel";
}

const student = new Student();

console.log(student.name); // Rasel
```

** like:** A school notice board that everyone can see.

## 2. Private – Accessible inside the class

`private` means a property or method can only be accessed within the class where it is defined. It cannot be used from outside the class.

```ts
class BankAccount {
  balance = 1000;

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

`protected` works like `private`. Child classes can also access the property or method.

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

** like:** A family secret that parents can share with their children but not with strangers.

## 4. Readonly – Cannot be changed

`readonly` allows a property to be read. Its value cannot be changed once it’s set.

```ts
class User {
  readonly id = 101;
}

const user = new User();

console.log(user.id); // 101

// user.id = 202; // Error
```

** like:** A school registration number that stays the same for life.

## Quick Comparison

| Modifier    | Inside Class | Child Class | Outside Class          |
| ----------- | ------------ | ----------- | ---------------------- |
| `public`    | Yes          | Yes         | Yes                    |
| `private`   | Yes          | No          | No                     |
| `protected` | Yes          | Yes         | No                     |
| `readonly`  | Readable     | Readable    | Readable, not writable |

**Note:** `readonly` controls whether you can change the value not if you can read it. You can combine `readonly` with `public` `private` or `protected`.

##

- `public`: Can be used anywhere.

- `private`: Can only be used inside the class.

- `protected`: Can be used inside the class or, by child classes.

- `readonly`: Cannot be changed after it is set.

Access modifiers help keep your code clean and easy to understand. They make it easier to control how class members are used, which helps with maintenance.
