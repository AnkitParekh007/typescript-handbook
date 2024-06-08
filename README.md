# TypeScript Methods and Features Reference

This project provides a comprehensive overview of commonly used TypeScript methods and features, grouped by their functionality, along with brief descriptions and usage examples.

## Basic Types

| TypeScript Type       | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| `boolean`             | Represents true/false values              | `let isDone: boolean = false;`                              |
| `number`              | Represents numeric values                 | `let decimal: number = 6;`                                  |
| `string`              | Represents text values                    | `let color: string = "blue";`                               |
| `array`               | Represents an array of values             | `let list: number[] = [1, 2, 3];`                           |
| `tuple`               | Represents an array with fixed number of elements of specific types | `let x: [string, number]; x = ["hello", 10];` |
| `enum`                | Represents a collection of related values | `enum Color {Red, Green, Blue}; let c: Color = Color.Green;`|
| `any`                 | Represents any type                       | `let notSure: any = 4; notSure = "maybe a string instead";` |
| `void`                | Represents the absence of a type          | `function warnUser(): void { console.log("This is my warning message"); }` |
| `null` and `undefined`| Represents null and undefined values      | `let u: undefined = undefined; let n: null = null;`         |

## Interfaces

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| `interface`           | Defines a contract for objects            | `interface LabeledValue { label: string; } function printLabel(labeledObj: LabeledValue) { console.log(labeledObj.label); }` |
| Optional Properties   | Properties that are optional in interfaces | `interface SquareConfig { color?: string; width?: number; }` |
| Readonly Properties   | Properties that cannot be modified        | `interface Point { readonly x: number; readonly y: number; }`|

## Functions

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| Function Types        | Defines types for functions               | `let myAdd: (x: number, y: number) => number = function(x: number, y: number): number { return x + y; };` |
| Optional Parameters   | Parameters that are optional in functions | `function buildName(firstName: string, lastName?: string) { if (lastName) return firstName + " " + lastName; else return firstName; }` |
| Default Parameters    | Parameters with default values            | `function buildName(firstName: string, lastName = "Smith") { return firstName + " " + lastName; }` |

## Classes

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| `class`               | Defines a class                           | `class Greeter { greeting: string; constructor(message: string) { this.greeting = message; } greet() { return "Hello, " + this.greeting; } }` |
| Inheritance           | Classes can inherit from other classes    | `class Animal { move(distanceInMeters: number = 0) { console.log(\`Animal moved \${distanceInMeters}m.\`); } } class Dog extends Animal { bark() { console.log('Woof! Woof!'); } }` |
| `super`               | Calls the constructor of the base class   | `class Dog extends Animal { constructor(name: string) { super(name); } }`                            |
| Public, Private, and Protected Modifiers | Access control keywords for class members | `class Animal { private name: string; public constructor(theName: string) { this.name = theName; } }` |

## Modules

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| `export`              | Exports a member from a module            | `export class ZipCodeValidator { isAcceptable(s: string) { return s.length === 5 && numberRegexp.test(s); } }` |
| `import`              | Imports a member from a module            | `import { ZipCodeValidator } from "./ZipCodeValidator";`    |

## Generics

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| Generics              | Enables creating components that work with any data type | `function identity<T>(arg: T): T { return arg; } let output = identity<string>("myString");` |

## Utility Types

| TypeScript Utility Type| Description                               | Example                                                     |
|------------------------|-------------------------------------------|-------------------------------------------------------------|
| `Partial`              | Constructs a type with all properties set to optional | `interface Todo { title: string; description: string; } function updateTodo (todo: Todo, fieldsToUpdate: Partial<Todo>) { return { ...todo, ...fieldsToUpdate }; }` |
| `Readonly`             | Constructs a type with all properties set to readonly | `interface Todo { title: string; } const todo: Readonly<Todo> = { title: "Delete inactive users" };` |

## Type Assertions

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| `as` syntax           | Tells the compiler to treat an entity as a different type | `let someValue: any = "this is a string"; let strLength: number = (someValue as string).length;` |

## Type Guards

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| `typeof`              | Type guard for primitive types            | `function padLeft(value: string, padding: string | number) { if (typeof padding === "number") { return Array(padding + 1).join(" ") + value; } if (typeof padding === "string") { return padding + value; } throw new Error(\`Expected string or number, got '\${padding}'.\`); }` |
| `instanceof`          | Type guard for class types                | `if (pet instanceof Dog) { pet.bark(); }`                    |

## Advanced Types

| TypeScript Feature    | Description                               | Example                                                     |
|-----------------------|-------------------------------------------|-------------------------------------------------------------|
| Intersection Types    | Combines multiple types into one          | `interface ErrorHandling { success: boolean; error?: { message: string; } } interface ArtworksData { artworks: { title: string; }[] } type ArtworksResponse = ErrorHandling & ArtworksData;` |
| Union Types           | A value can be one of several types       | `function printId(id: number | string) { console.log("Your ID is: " + id); }` |

This document provides a quick reference to commonly used TypeScript methods and features. For more detailed information, refer to the [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/).
