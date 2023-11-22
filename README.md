# Introduction

**`Angular`** is a popular open-source web application framework developed and maintained by Google and a community of developers. It is written in TypeScript and allows developers to build dynamic, single-page web applications (SPAs) with a rich user interface. Here are some key reasons why Angular is widely used and its main purposes:

1. **`Declarative UI`**:
Angular uses HTML as the template language and extends its syntax to express the components of your application in a clear and declarative manner. This makes it easier to understand and maintain the structure of your application.

2. **`Two-way Data Binding`**:
Angular provides two-way data binding, which means that changes in the user interface (UI) are automatically reflected in the application's data model and vice versa. This simplifies the synchronization of the UI and the underlying data.

3. **`Modularity`**:
Angular encourages the development of modular applications. You can break down your application into smaller, reusable components, which makes it easier to manage and scale your codebase.

4. **`Dependency Injection`**:
Angular has a built-in dependency injection system that helps manage the components and services in your application. This promotes the development of loosely coupled and highly maintainable code.

5. **`MVVM Architecture`**:
Angular follows the Model-View-ViewModel (MVVM) architecture, where the model represents the application's data, the view displays the data, and the view-model manages the communication between the view and the model. This separation of concerns enhances code organization and maintainability.

6. **`Cross-browser Compatibility`**:
Angular takes care of many cross-browser compatibility issues, allowing developers to focus on building features rather than dealing with browser-specific quirks.

7. **`Built-in Directives and Pipes`**:
Angular provides a set of built-in directives and pipes that make it easy to manipulate the DOM, format data, and perform various operations within your templates.

8. **`Testing`**:
Angular is designed with testability in mind. It comes with built-in testing utilities and supports tools like Jasmine and Karma for writing and running tests. This makes it easier to ensure the reliability and correctness of your code.

9. **`Rich Ecosystem`**:
Angular has a large and active community, as well as a rich ecosystem of libraries, tools, and extensions that can be leveraged to enhance development productivity.

In summary, **`Angular`** is a powerful framework for building dynamic and modular web applications. It provides a structured approach to development, making it easier to create and maintain large-scale applications while offering features like two-way data binding, dependency injection, and a rich set of tools for testing and development.

# Lifecycle Hooks

Angular, a popular web application framework, provides a set of **`lifecycle hooks`** that allow you to tap into different phases of a component's lifecycle. These hooks enable you to perform actions at specific points in the life of a component, such as **`initialization`**, **`change detection`**, and **`destruction`**.

Here is an overview of some of the key Angular lifecycle hooks:

1. **`ngOnChanges`**:

This hook is called when an input property of a component changes.
It receives a **`SimpleChanges`** object that contains information about the changed properties.

```typescript
ngOnChanges(changes: SimpleChanges) {
  // React to input property changes
}
```

2. **`ngOnInit`**:

* This hook is called once when the component is initialized.
* It is commonly used for initialization logic, such as retrieving data from a service.

```typescript
ngOnInit() {
  // Component initialization logic
}
```

3. **`ngDoCheck`**:

* This hook is called during every change detection cycle.
* It allows you to implement custom change detection logic.

```typescript
ngDoCheck() {
  // Custom change detection logic
}
```

4. **`ngAfterContentInit`**:

* This hook is called after Angular has projected external content into the component's view.
* It is commonly used when a component needs to interact with content projected into it.

```typescript
ngAfterContentInit() {
  // After content initialization logic
}
```

5. **`ngAfterContentChecked`**:

* This hook is called after Angular checks the content projected into the component.
* It can be used for additional checks or actions after content initialization.

```typescript
ngAfterContentChecked() {
  // After content checked logic
}
```

6. **`ngAfterViewInit`**:

* This hook is called after the component's view has been initialized.
* It is often used for operations that require access to the component's view or its child views.

```typescript
ngAfterViewInit() {
  // After view initialization logic
}
```

7. **`ngAfterViewChecked`**:

* This hook is called after Angular checks the component's view and child views.
* It is used for additional checks or actions after view initialization.

```typescript
ngAfterViewChecked() {
  // After view checked logic
}
```

8. **`ngOnDestroy`**:

* This hook is called just before the component is destroyed.
* It is used for cleanup activities such as unsubscribing from observables to avoid memory leaks.

```typescript
ngOnDestroy() {
  // Cleanup logic before component destruction
}
```

By implementing these lifecycle hooks in your Angular components, you can control the behavior of your components at different stages of their lifecycle. This allows you to perform setup, update, and cleanup tasks as needed.

# TypeScript

**`TypeScript`** is a programming language that is a superset of JavaScript, meaning that all valid JavaScript code is also valid TypeScript code. However, TypeScript extends JavaScript by adding static typing to the language. This allows developers to define types for variables, function parameters, and return types, which can help catch errors during development and provide better tooling support.

Key features of TypeScript include:

1. **`Static Typing`**: TypeScript introduces a static type system, enabling developers to define types for variables, function parameters, and return values. This helps catch type-related errors during development and provides better code intelligence in integrated development environments (IDEs).

2. **`Interfaces`**: TypeScript supports the use of interfaces, allowing developers to define contracts for object shapes. This enhances code readability and maintainability by explicitly specifying the expected structure of objects.

3. **`Enums`**: TypeScript includes support for enums (enumerations), making it easier to work with sets of named constants. This can improve code clarity by giving meaningful names to values.

4. **`Classes`**: TypeScript supports the class-based object-oriented programming paradigm, which is a more structured and organized way to write code, especially for larger applications.

5. **`Modules`**: TypeScript has a module system that helps organize code into separate files and namespaces, making it easier to manage and maintain large codebases.

6. **`Generics`**: TypeScript allows the use of generics, enabling developers to write more reusable and flexible code by creating functions and classes that can work with a variety of data types.

7. **`Compile-time Checking`**: TypeScript code is transpiled to JavaScript before execution, and during this process, the TypeScript compiler performs static type checking. This means that many potential errors can be caught at compile time rather than runtime.

Developers often choose TypeScript for projects where a strong type system is desired to catch errors early in the development process, especially in larger codebases. TypeScript code can be compiled to JavaScript, making it compatible with existing JavaScript projects and allowing gradual adoption of TypeScript features.

# Difference between TypeScript Constructor and Angular OnInit Lifecycle Hook

In Angular, the **`constructor`** and **`ngOnInit`** are two different methods used in a component's lifecycle, and they serve different purposes.

1. **`Constructor`**:

* The **`constructor`** is a **`TypeScript feature`** and is part of the class itself rather than Angular's lifecycle hooks.
* It is executed when an instance of the component is created.
* It is primarily used for dependency injection and initialization of class-level properties.
* It is not specific to Angular and is a standard part of the TypeScript class.

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<p>{{ message }}</p>'
})
export class ExampleComponent {
  message: string;

  constructor() {
    this.message = 'Hello, world!';
  }
}
```

2. **`ngOnInit`**:

**`ngOnInit`** is a **`lifecycle hook`** provided by Angular. It is part of the Angular component lifecycle and is called after the component has been initialized.
It is commonly used for tasks that need to be performed after the component has been created, such as fetching data from a server or initializing properties that depend on input values.
It is not responsible for creating the component, but rather for initializing it after Angular has created it.

Example:

```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-example',
  template: '<p>{{ message }}</p>'
})
export class ExampleComponent implements OnInit {
  message: string;

  constructor() {
    // Constructor code runs before ngOnInit
  }

  ngOnInit() {
    // ngOnInit is called after the component has been initialized
    this.message = 'Hello, world!';
  }
}
```

In summary, the **`constructor`** is a **`standard TypeScript feature`** used for basic setup and dependency injection, while **`ngOnInit`** is an **`Angular lifecycle hook`** specifically designed for more complex initialization tasks after the component has been created.

# Commands

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 17.0.1.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
