# Demo Manual

![Angular Logo](./angular_solidBlack.png)

<br /><br /><br /><br /><br />

Copyright © 2023-2025

Funny Ant, LLC

All rights reserved.

No part of this book may be reproduced in any form or by any electronic or mechanical means including
information storage and retrieval systems, without permission from the author.

<div style="page-break-after: always;"></div>

## Table of Contents

- [Demo Manual](#demo-manual)
  - [Table of Contents](#table-of-contents)
  - [Understanding this Manual](#understanding-this-manual)
  - [Overview](#overview)
    - [Getting Started](#getting-started)
    - [Reset](#reset)
    - [External vs. Inline Styles](#external-vs-inline-styles)
  - [Components](#components)
    - [First & Templates (Internal vs. External)](#first--templates-internal-vs-external)
    - [Nesting](#nesting)
  - [Modules](#modules)
    - [Declarations](#declarations)
    - [Imports & Exports (Feature Modules)](#imports--exports-feature-modules)
  - [Components (continued...)](#components-continued)
    - [JSON Pipe](#json-pipe)
    - [ngFor](#ngfor)
    - [Interpolation](#interpolation)
    - [Property Binding](#property-binding)
    - [Input Properties](#input-properties)
    - [Event Binding](#event-binding)
    - [Pipes](#pipes)
    - [Output Events](#output-events)
    - [Component Styling](#component-styling)
    - [ngIf](#ngif)
    - [ngSwitch](#ngswitch)
  - [Forms](#forms)
    - [Reactive Forms Binding](#reactive-forms-binding)
    - [Reactive Forms Validation](#reactive-forms-validation)
      - [UpdateOn](#updateon)
    - [Reactive Forms Validation Messages](#reactive-forms-validation-messages)
    - [Reactive Forms Custom Validator](#reactive-forms-custom-validator)
    - [ngClass](#ngclass)
      - [Displaying Validation Messages](#displaying-validation-messages)
  - [Services](#services)
  - [RxJS](#rxjs)
    - [Observables](#observables)
      - [Creating a Stream of DOM Events](#creating-a-stream-of-dom-events)
      - [Listening for keyup events](#listening-for-keyup-events)
    - [Observers](#observers)
    - [Subcriptions](#subcriptions)
    - [Operators](#operators)
      - [map](#map)
      - [tap](#tap)
      - [filter](#filter)
    - [Subjects](#subjects)
      - [Read & Write](#read--write)
      - [Multicast](#multicast)
      - [Unicast Observable Demo](#unicast-observable-demo)
      - [Multicast](#multicast-1)
      - [Multicast Subject Example](#multicast-subject-example)
    - [Practical Example](#practical-example)
      - [debounceTime](#debouncetime)
      - [distinctUntilChanged](#distinctuntilchanged)
      - [switchMap](#switchmap)
  - [Additional Reading](#additional-reading)
  - [Http](#http)
    - [Get](#get)
    - [Error Handling](#error-handling)
    - [Retry](#retry)
  - [Routing](#routing)
    - [Routing Basics](#routing-basics)
      - [`app.component.ts`](#appcomponentts)
    - [Routing Navigation](#routing-navigation)
      - [Code Review](#code-review)
      - [Routing Changes](#routing-changes)
  - [Routing (Advanced)](#routing-advanced)
    - [Child Routes](#child-routes)
    - [Lazy Loading](#lazy-loading)
  - [Components (Advanced)](#components-advanced)
    - [Change Detection](#change-detection)
      - [Checkout](#checkout)
      - [ChangeDetectionStrategy.Default](#changedetectionstrategydefault)
      - [ChangeDetectionStrategy.OnPush](#changedetectionstrategyonpush)
- [Appendixes](#appendixes)
  - [Redux (NgRx)](#redux-ngrx)
    - [Redux (NgRx) Counter](#redux-ngrx-counter)
      - [Setup](#setup)
      - [Installation](#installation)
      - [Store](#store)
      - [Actions](#actions)
      - [Reducer](#reducer)
      - [User Interface](#user-interface)
    - [NgRx Lab](#ngrx-lab)
      - [Setup](#setup-2)
      - [Installation](#installation-2)
      - [Actions](#actions-2)
      - [State](#state)
      - [Reducer](#reducer-2)
      - [Effects](#effects)
      - [Configure](#configure)
      - [Connect the Container & Store](#connect-the-container--store)
    - [NgRx Resources](#ngrx-resources)
      - [Online courses](#online-courses)
      - [Redux & GraphQL Resources](#redux--graphql-resources)
  - [Template-driven Forms](#template-driven-forms)
    - [Template Forms Binding](#template-forms-binding)
    - [Template Forms Validation](#template-forms-validation)
      - [Displaying Validation Messages](#displaying-validation-messages-1)
    - [Two-way Binding](#two-way-binding)
  - [Angular Material: Introduction](#angular-material-introduction)
    - [Installation](#installation-3)
    - [Navigation](#navigation)
    - [Dashboard](#dashboard)
    - [Table](#table)
    - [Forms](#forms-1)
      - [Reference](#reference)
  - [Angular Material: CDK](#angular-material-cdk)
    - [CDK: Installation](#cdk-installation)
      - [Steps](#steps)
    - [CDK: Drag & Drop](#cdk-drag--drop)
      - [Steps](#steps-1)
      - [Reorder List](#reorder-list)
    - [CDK: Virtual Scrolling](#cdk-virtual-scrolling)
      - [Steps](#steps-2)
      - [Resources](#resources)
    - [Bootstrapping an Application](#bootstrapping-an-application)
  - [Lifecycle Hooks](#lifecycle-hooks)
    - [Starting Point](#starting-point)
    - [Init & Changes](#init--changes)
    - [Destroy](#destroy)
    - [Final Code](#final-code)
    - [ViewChild(ren) & AfterViewInit](#viewchildren--afterviewinit)
    - [ContentChild(ren) & AfterContentInit](#contentchildren--aftercontentinit)
    - [Reference](#reference-1)
  - [Libraries](#libraries)
    - [Your First Library](#your-first-library)
    - [Issues](#issues)
    - [Reference](#reference-2)
  - [IVY](#ivy)
    - [Using Ivy in an existing project](#using-ivy-in-an-existing-project)
  - [Resources](#resources-1)
  - [Setup](#setup-3)
    - [Creating this project](#creating-this-project)
    - [Creating the http-start branch](#creating-the-http-start-branch)
  - [Feedback](#feedback)

<div style="page-break-after: always;"></div>

## Understanding this Manual

## Overview

This is the demo manual and is **not provided to attendees until the end of class**. It's purpose is to provide step-by-step directions for instructor demonstrations (demos) used in class.

Attendees do, however, receive the finished code for each demonstration at the beginning of class as part of the course files zip.

It is **recommended that the instructor print a hard copy** of this demo manual and use it as a reference to complete the demonstrations.

<div style="page-break-after: always;"></div>

### Getting Started

1. Clone this repository: https://github.com/craigmckeachie/a16_demos
2. Open `a16_demos` as the top level folder in your editor.
3. Open a command-prompt or terminal in `a12_demos` and run the command.

```shell
npm install
```

3. Build and start the demo application by running the following command.

```shell
ng serve -o
```

You can leave `ng serve` running when changing between demos or writing code and it will automatically rebuild your code and reload the browser so you can see your changes.

<div style="page-break-after: always;"></div>

### Reset

After starting a demo you will need to reset the code before beginning the next demo.
You can do this by running the following commands.

```shell
git checkout start -f //checks out the start branch
git clean -df // removes untracked directories and files df
```

For more information see this link about [git-clean](https://stackoverflow.com/questions/61212/how-to-remove-local-untracked-files-from-the-current-git-working-tree)

<div style="page-break-after: always;"></div>

### External vs. Inline Styles

**IMPORTANT**

The demos project uses inline templates and inline styles (the html and css is write in the ts file).
This is intentional as it greatly helps students see the connection between code in the html and the ts file.

In addition, we have found that when learning...less files equals less confusion.

The official Angular Style Guide recommends to **Extract templates and styles to their own files** (i.e. external templates and styles).

> This recommendation IS followed in the student labs to teach best practices.

> This recommendation is NOT followed in the demos to facilitate learning.

> Reference: Angular Style Guide: Extract templates and styles to their own files
>
> - https://angular.io/guide/styleguide#extract-templates-and-styles-to-their-own-files

Accordingly, this project was created using the following command and it can be useful to explain this before doing the first demo.

```
ng new demos --routing --inline-style --strict=false --inline-template --skip-tests
```

<div style="page-break-after: always;"></div>

## Components

### First & Templates (Internal vs. External)

```shell
ng g component hello-world -d
```

`app.component.ts`

```ts
@Component({
  selector: "app-root",
  template: ` <app-hello-world></app-hello-world> `,
  styles: [],
})
export class AppComponent {}
```

create the file `hello-world/hello-world.component.html`

```html
<p>hello-world still works!</p>
```

`app.component.ts`

```diff
@Component({
  selector: 'app-hello-world',
+  templateUrl: `./hello-world.component.html`,
  styles: []
})
export class HelloWorldComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

<div style="page-break-after: always;"></div>

### Nesting

```
ng g component my-button
```

Point out that it was added to app.module.ts declarations

`hello-world/hello-world.component.html`

```diff
<p>
  hello-world still works!
+ <app-my-button></app-my-button>
</p>
```

<div style="page-break-after: always;"></div>

## Modules

### Declarations

```shell
ng g c tag-one
```

Show how component was added to the `declarations` in the app module.

`app.module.ts`

```diff
+ import { TagOneComponent } from './tag-one.component';
...
@NgModule({
  declarations: [AppComponent,
+              TagOneComponent]
  ...
})
```

```shell
ng g c tag-one
ng g c tag-two
ng g c tag-three
```

Add new component selectors/tags to the app.component template.

```ts
@Component({
  selector: "app-root",
  template: `
    <app-tag-one></app-tag-one>
    <app-tag-two></app-tag-two>
    <app-tag-three></app-tag-three>
  `,
  styles: [],
})
export class AppComponent {}
```

<div style="page-break-after: always;"></div>

### Imports & Exports (Feature Modules)

```ts
ng g module orders
ng g c orders/order-list
ng g c orders/order-detail
ng g c orders/order-form
ng g service orders/shared/order
//note that the service is injected in root we'll talk about that later
ng g pipe orders/shared/order-number
```

import orders module in app module

```diff
+ import { OrdersModule } from './orders/orders.module';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule,
+            OrdersModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

- Exports
  add `project-detail` to app component template

`app.component.ts`

```diff
@Component({
  selector: 'app-root',
  template: `
+   <app-order-detail></app-order-detail>
  `,
  styles: []
})
export class AppComponent {}
```

- doesn't work yet

<div style="page-break-after: always;"></div>

- export project-detail component

`orders\orders.module.ts`

```diff
@NgModule({
  imports: [CommonModule],
  declarations: [
    OrderListComponent,
    OrderDetailComponent,
    OrderFormComponent,
    OrderNumberPipe
  ],
+  exports: [OrderDetailComponent]
})
export class OrdersModule {}
```

- Now it should render `order detail works`.

<div style="page-break-after: always;"></div>

## Components (continued...)

### JSON Pipe

Just start with the solution branch and remove and add back the couple lines showing the `json pipe`.

```shell
git checkout json-pipe -f
```

```ts
@Component({
  selector: "app-root",
  template: `
    <div>
      <p>Without JSON pipe:</p>
      <p>{{ object }}</p>
      <p>With JSON pipe (no pre tag):</p>
      <p>{{ object | json }}</p>
      <p>With JSON pipe (and pre tag):</p>
      <pre>{{ object | json }}</pre>
    </div>
  `,
  styles: [],
})
export class AppComponent {
  object: Object = {
    foo: "bar",
    baz: "qux",
    nested: { xyz: 3, numbers: [1, 2, 3, 4, 5] },
  };
}
```

<div style="page-break-after: always;"></div>

### ngFor

```ts
@Component({
  selector: "app-root",
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">{{ fruit }}</li>
    </ul>
  `,
  styles: [],
})
export class AppComponent {
  fruits = ["Apple", "Orange", "Plum"];
}
```

```diff
+  <li *ngFor="let fruit of fruits; let i = index;">
    {{i + 1}}.
    {{fruit}}
  </li>
```

The Angular logo used for this demonstration is available in the `src\assets` directory of the start branch.

### Interpolation

```ts
@Component({
  selector: "app-root",
  template: `
    <h2>{{ image.name }}</h2>
    <p>{{ image.path }}</p>
  `,
  styles: [],
})
export class AppComponent {
  image = {
    path: "../assets/angular_solidBlack.png",
    name: "Angular Logo",
  };
}
```

<div style="page-break-after: always;"></div>

### Property Binding

```ts
@Component({
  selector: "app-root",
  template: `
    <img [src]="image.path" [alt]="image.name" [title]="image.name" />
  `,
  styles: [],
})
export class AppComponent {
  image = {
    path: "../assets/angular_solidBlack.png",
    name: "Angular Logo",
  };
}
```

<div style="page-break-after: always;"></div>

### Input Properties

```shell
git checkout ngFor -f
```

Generate a list component.

```shell
ng g component fruit-list
```

```ts
// fruit-list/fruit-list.component.ts

import { Component, OnInit, Input } from "@angular/core";

@Component({
  selector: "app-fruit-list",
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">{{ fruit }}</li>
    </ul>
  `,
  styles: [],
})
export class FruitListComponent implements OnInit {
  @Input()
  fruits: string[];
  constructor() {}

  ngOnInit() {}
}
```

`app.component.ts`

```ts
@Component({
  selector: "app-root",
  template: ` <app-fruit-list [fruits]="data"></app-fruit-list> `,
  styles: [],
})
export class AppComponent {
  data: string[] = ["Apple", "Orange", "Plum"];
}
```

<div style="page-break-after: always;"></div>

### Event Binding

```ts
@Component({
  selector: "app-root",
  template: `
    <a href="" (click)="onClick($event)">Click Me!</a>
    <p [innerText]="message"></p>
  `,
  styles: [],
})
export class AppComponent {
  message = "";

  onClick(event) {
    event.preventDefault();
    this.message = "clicked";
  }
}
```

<div style="page-break-after: always;"></div>

### Pipes

```shell
git checkout pipes -f
```

```ts
@Component({
  selector: "app-root",
  template: `
    <table>
      <tr>
        <th>Pipe Expression</th>
        <th>Formatted Output</th>
      </tr>
      <tr>
        <td>amount | currency: 'USD': "symbol": '2.1-2'</td>
        <td>{{ amount | currency : "USD" : "symbol" : "2.1-2" }}</td>
      </tr>
      <tr>
        <td>releaseDate | date : 'MM/dd/yyyy'</td>
        <td>{{ releaseDate | date : "MM/dd/yyyy" }}</td>
      </tr>
      <tr>
        <td>amount | number: '3.3-4'</td>
        <td>{{ amount | number : "3.3-4" }}</td>
      </tr>
      <tr>
        <td>percentOfGross | percent: '2.2'</td>
        <td>{{ percentOfGross | percent : "2.2" }}</td>
      </tr>
    </table>
  `,
  styles: [],
})
export class AppComponent {
  amount = 47.341;
  releaseDate: Date = new Date(1975, 4, 25);
  percentOfGross = 0.3245;
}
```

<div style="page-break-after: always;"></div>

### Output Events

```
ng g component email-subscribe
```

```ts
// email-subscribe.ts

import { Component, OnInit, Output, EventEmitter } from "@angular/core";

@Component({
  selector: "app-email-subscribe",
  template: `
    <input type="text" #email placeholder="email" />
    <button (click)="onClick(email.value)">Subscribe</button>
  `,
  styles: [],
})
export class EmailSubscribeComponent implements OnInit {
  @Output()
  subscribe = new EventEmitter<string>();
  constructor() {}

  ngOnInit() {}
  onClick(email: string) {
    this.subscribe.emit(email);
  }
}
```

```ts
// app.component.ts
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `
    <app-email-subscribe
      (subscribe)="onSubscribe($event)"
    ></app-email-subscribe>
    {{ message }}
  `,
  styles: [],
})
export class AppComponent {
  message: string;
  onSubscribe(email) {
    this.message = `Successfully subscribed. Please check your email ${email} and click link.`;
  }
}
```

<div style="page-break-after: always;"></div>

### Component Styling

- Inline
  `app.component.ts`

```ts
styles: [
  `
    h1 {
      color: rgb(255, 165, 0);
    }
  `,
];
```

- External
  `app.component.ts`

```ts
@Component({
  selector: "app-root",
  template: ` <h1>Welcome to {{ title }}!</h1> `,
  styleUrls: ["./app.component.css"],
})
export class AppComponent {
  title = "playground";
}
```

`app.component.css`

```css
h1 {
  color: rgb(255, 165, 0);
}
```

<div style="page-break-after: always;"></div>

### ngIf

```ts
@Component({
  selector: "app-root",
  template: `
    <div>
      <input type="text" placeholder="username" />
      <input type="text" placeholder="password" />
      <button (click)="signIn()">Sign In</button>
    </div>

    <div>Welcome back friend.</div>
  `,
  styles: [],
})
export class AppComponent {
  isSignedIn = false;

  signIn() {
    this.isSignedIn = true;
  }
}
```

```diff
  <div
+  *ngIf="isSignedIn">
  Welcome back friend.
  </div>
```

```diff
  <div
+  *ngIf="!isSignedIn">
  <input type="text" placeholder="username">
  ...
```

<div style="page-break-after: always;"></div>

- ngIf; else

```diff
@Component({
  selector: 'app-root',
  template: `
  <div
+ *ngIf="!isSignedIn; else signedIn">
  <input type="text" placeholder="username">
  <input type="text" placeholder="password">
  <button (click)="signIn()">Sign In</button>
  </div>

+ <ng-template #signedIn>
  <div>
  Welcome back friend.
  </div>
+ </ng-template>
  `,
  styles: []
})
```

<div style="page-break-after: always;"></div>

### ngSwitch

```
git checkout ngFor -f
```

```html
<div [ngSwitch]="fruits.length">
  <p *ngSwitchCase="0">No records returned.</p>
  <p *ngSwitchCase="1">1 record returned.</p>
  <p *ngSwitchDefault>{{fruits.length}} records were returned.</p>
</div>
```

<div style="page-break-after: always;"></div>

## Forms

### Reactive Forms Binding

`app.module.ts`

```diff
+ import { ReactiveFormsModule } from '@angular/forms';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule,
+           ReactiveFormsModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

> Note: You may have to manually type the import

<div style="page-break-after: always;"></div>

> It is easier to understand to type the component code first, then the template.

`app.component.ts`

```ts
import { Component, OnInit } from "@angular/core";
import { FormGroup, FormControl } from "@angular/forms";
@Component({
  selector: "app-root",
  template: `
    <h1>Forms</h1>
    <form [formGroup]="loginForm" (submit)="onSubmit()">
      <input formControlName="username" type="text" name="username" /> <br />
      <input formControlName="password" type="text" name="password" /> <br />
      <button>Sign In</button>
    </form>
    <pre>
    {{ loginForm.value | json }}
  </pre
    >
  `,
  styles: [],
})
export class AppComponent implements OnInit {
  loginForm: FormGroup;
  ngOnInit(): void {
    this.loginForm = new FormGroup({
      username: new FormControl(),
      password: new FormControl(),
    });
  }
  onSubmit() {
    console.log(this.loginForm.value);
  }
}
```

<div style="page-break-after: always;"></div>

### Reactive Forms Validation

`app.component.ts`

```diff
export class AppComponent implements OnInit {
loginForm: FormGroup;
ngOnInit(): void {
  this.loginForm = new FormGroup(
    {
      username: new FormControl(null,
+ Validators.required),
      password: new FormControl()
    });
}
onSubmit() {
  console.log(this.loginForm.value);
}
}
```

`app.component.html`

```html
...
<pre *ngIf="loginForm.get('username').invalid">
{{loginForm.get('username').errors | json}}
</pre>
```

1. See validation errors on refresh.
2. Enter username.
3. Error does not display.
4. Delete username see error displayed again.

<div style="page-break-after: always;"></div>

#### UpdateOn

`app.component.ts`

```diff
  export class AppComponent implements OnInit {
  loginForm: FormGroup;
  ngOnInit(): void {
    this.loginForm = new FormGroup(
      {
        username: new FormControl(null, Validators.required),
        password: new FormControl()
      },
+     { updateOn: 'blur' }
    );
  }
  onSubmit() {
    console.log(this.loginForm.value);
  }
  }
```

<div style="page-break-after: always;"></div>

### Reactive Forms Validation Messages

`app.component.html`

```html
...
<div
  *ngIf="loginForm.get('username')?.dirty &&
loginForm.get('username')?.invalid &&
loginForm.get('username')?.touched"
>
  <div *ngIf="loginForm.get('username')?.hasError('required')">
    Username is required.
  </div>
</div>
```

> Creating the inner `div` first and then wrapping with the outer `div` can facilitate understanding.

Follow these steps to display the validation message. This is intentional but can be confusing.

- Enter some text in the email field
- Delete the text
- Tab out of the email input or cause the email input to lose focus in some way

<div style="page-break-after: always;"></div>

### Reactive Forms Custom Validator

Validate password doesn't contain the phrase password "password".

- Start with this branch

```shell
git checkout reactive-forms-validation
```

- Output password validation errors

```html
<pre *ngIf="loginForm.get('password')?.invalid">
 {{loginForm.get('password').errors | json}}
 </pre
>
```

- Create Custom validator

Do this in the `app.component.ts` file to make it easier to follow the code.

```ts
export class CustomValidators {
  static forbiddenPhrase(control: AbstractControl): ValidationErrors | null {
    if (control.value) {
      if (control.value.toLowerCase() === "password") {
        return { forbiddenPhrase: true };
      }
    }
    return null;
  }

  // create method signature
  // paste existing validation function, convert inner function to arrow by removing name and adding => before opening curly brace
  // add semi-colon at the end
  // remove hard-coded phrase
  static forbiddenPhraseValidatorFn(phrase: string): ValidatorFn {
    return (control: AbstractControl): ValidationErrors | null => {
      if (control.value) {
        if (control.value.toLowerCase() === phrase) {
          return { forbiddenPhrase: true };
        }
      }
      return null;
    };
  }
}
```

- Add custom validator.
  `app.component.ts`

```diff
import { Component, OnInit } from '@angular/core';
import {
  FormGroup,
  FormControl,
  Validators,
  AbstractControl,
  ValidatorFn,
  ValidationErrors
} from '@angular/forms';
...
export class AppComponent implements OnInit {
  loginForm: FormGroup;
  ngOnInit(): void {
    this.loginForm = new FormGroup(
      {
        username: new FormControl(null, Validators.required,
        password: new FormControl(
          null,
+          CustomValidators.forbiddenPhraseValidatorFn('password')
        )
      }
+      // { updateOn: 'blur' }
    );
  }
  onSubmit() {
    console.log(this.loginForm.value);
  }
}
```

<div style="page-break-after: always;"></div>

### ngClass

```ts
@Component({
  selector: "app-root",
  template: ` <p>We need to button up our approach out of the loop...</p> `,
  styles: [
    `
      .highlight {
        background-color: #ffff00;
      }
    `,
  ],
})
export class AppComponent {}
```

```diff
@Component({
  selector: 'app-root',
  template: `
+    <p (click)="onClick()" [class.highlight]="isHighlighted">
    We need to button...
    </p>
  `,
  styles: [
    `
      .highlight {
        background-color: #ffff00;
      }
    `
  ]
})
export class AppComponent {
+  isHighlighted = false;
+  onClick() {
+    this.isHighlighted = !this.isHighlighted;
+  }
}
```

<div style="page-break-after: always;"></div>

```diff
@Component({
  selector: 'app-root',
  template: `
    <p (click)="onClick()" [class.highlight]="isHighlighted"
+   [class.underline]="true">
    We need to button ...
    </p>
  `,
  styles: [
    `
      .highlight {
        background-color: #ffff00;
      }
+     .underline {
+       text-decoration: underline;
+     }
    `
  ]
})
export class AppComponent {
  isHighlighted = false;
  onClick() {
    this.isHighlighted = !this.isHighlighted;
  }
}
```

```diff
@Component({
  selector: 'app-root',
  template: `
    <p (click)="onClick()"
+    [ngClass]="calculateClasses()">
    We need to button up ...
    </p>
  `,
  styles: [
    `
      .highlight {
        background-color: #ffff00;
      }
      .underline {
        text-decoration: underline;
      }
    `
  ]
})
export class AppComponent {
  isHighlighted = false;

  onClick() {
    this.isHighlighted = !this.isHighlighted;
  }

+  calculateClasses() {
+    return {
+      highlight: this.isHighlighted,
+      underline: true
+    };
+ }
}
```

<div style="page-break-after: always;"></div>

- ngStyle

```html
<p (click)="onClick()" [style.background-color]="'orchid'">
  We need to button up ...
</p>
```

```html
<p
  [ngStyle]="{'background-color': 'lime',
    'font-size': '20px',
    'font-weight': 'bold'}"
>
  Here we go...
</p>
```

<div style="page-break-after: always;"></div>

```diff
// app.component.ts

import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
  <form #signinForm="ngForm" (submit)="onSubmit(signinForm)">
      <input
        type="text"
        placeholder="username"
        ngModel
+        #username="ngModel"
        name="username"
+        required
+        minlength="3"
      /><br />
+      <pre>
+        {{ username.errors | json }}
+      </pre
      >
+      <br />
+      Dirty: {{ username.dirty | json }} <br />
+      Touched: {{ username.touched | json }} <br />
      <input type="text" ngModel name="password" placeholder="password" /><br />
      <button>Sign In</button>
    </form>
  `,
  styles: []
})
export class AppComponent {
  ...
}
```

<div style="page-break-after: always;"></div>

#### Displaying Validation Messages

```diff
// app.component.ts

@Component({
  selector: 'app-root',
  template: `
    <form #signinForm="ngForm" (submit)="onSubmit(signinForm)">
      <input
        type="text"
        placeholder="username"
        ngModel
        #username="ngModel"
        name="username"
        required
        minlength="3"
      /><br />
+      <div *ngIf="username.hasError('required') && username.dirty">
+        Username is required.
+      </div>

-      <pre>
-        {{ username.errors | json }}
-      </pre>
-      <br />
-      Dirty: {{ username.dirty | json }} <br />
-      Touched: {{ username.touched | json }} <br />
      <input type="text" ngModel name="password" placeholder="password" /><br />

      <button>Sign In</button>
    </form>
  `,
  styles: []
})
export class AppComponent {
...
}
```

<div style="page-break-after: always;"></div>

## Services

- Setup

```shell
git checkout ngFor
```

- Create & Register Service

```shell
ng g service fruit
```

```ts
// fruit.service.ts
import { Injectable } from "@angular/core";

@Injectable({
  providedIn: "root",
})
export class FruitService {
  constructor() {}

  list(): string[] {
    return ["Apple", "Orange", "Plum"];
  }
}
```

- Inject Service

```diff
// app.component.ts
export class AppComponent implements OnInit {
-  fruits = ['Apple', 'Orange', 'Plum'];
+  fruits = [];

+  constructor(private fruitService: FruitService) {}

+  ngOnInit(): void {
+    this.fruits = this.fruitService.list();
+  }
}
```

<div style="page-break-after: always;"></div>

- With an Observable to handle async

```ts
// fruit.service.ts
import { Injectable } from "@angular/core";
import { of, Observable } from "rxjs";

@Injectable({
  providedIn: "root",
})
export class FruitService {
  constructor() {}

  list(): Observable<string[]> {
    return of(["Apple", "Orange", "Plum"]);
  }
}
```

```ts
// app.component.ts
export class AppComponent implements OnInit {
  fruits = [];

  constructor(private fruitService: FruitService) {}

  ngOnInit(): void {
    this.fruitService.list().subscribe((data) => (this.fruits = data));
  }
}
```

<div style="page-break-after: always;"></div>

- See Async Happening

```diff
import { Injectable } from '@angular/core';
import { of, Observable } from 'rxjs';
+ import { delay } from 'rxjs/operators';

@Injectable({
  providedIn: 'root'
})
export class FruitService {
  constructor() {}

  list(): Observable<string[]> {
    return of(['Apple', 'Orange', 'Plum'])
+    .pipe(delay(4000));
  }
}
```

```diff
ngOnInit(): void {
    this.fruitService.list().subscribe(data => (this.fruits = data));
+    console.log('completed OnInit');
  }
```

1. Run the application.
2. Open Chrome Devtools.
3. Because we added a 4 second delay, you will see `completed OnInit` logged before the data loads on the page.

<div style="page-break-after: always;"></div>

## RxJS

### Observables

**Observable**: represents the idea of an invokable collection of future values or events.

```diff
import { Component, OnInit } from '@angular/core';
+ import { of } from 'rxjs';

@Component({
  selector: 'app-root',
  template: ``,
  styles: []
})
export class AppComponent implements OnInit {
+  ngOnInit(): void {
+    const observable$ = of(1, 2, 3);
+    observable$.subscribe(x => console.log(x));
+  }
}
```

OR

```diff
export class AppComponent implements OnInit {
+  ngOnInit(): void {
+    of(1, 2, 3).subscribe(x => console.log(x));
+  }
}
```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser

```
1
2
3
```

<div style="page-break-after: always;"></div>

#### Creating a Stream of DOM Events

```diff
import { Component, OnInit, ViewChild } from '@angular/core';
import { of,
+ fromEvent } from 'rxjs';

@Component({
  selector: 'app-root',
  template: `
+    <button #myButton>Click Me</button>
  `,
  styles: []
})
export class AppComponent implements OnInit {
  @ViewChild('myButton', { static: true }) button;
  ngOnInit(): void {
+    console.log(this.button);
+    const clicks$ = fromEvent(this.button.nativeElement, 'click');
+    clicks$.subscribe(event => console.log(event));
  }
}

```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser
- Click the button on the page

```
MouseEvent {isTrusted: true, screenX: 30, screenY: 101, clientX: 30, clientY: 22, …}
MouseEvent {isTrusted: true, screenX: 30, screenY: 101, clientX: 30, clientY: 22, …}
...
```

<div style="page-break-after: always;"></div>

#### Listening for keyup events

```ts
import { Component, OnInit, ViewChild } from "@angular/core";
import { fromEvent } from "rxjs";

@Component({
  selector: "app-root",
  template: ` <input #myInput /> `,
  styles: [],
})
export class AppComponent implements OnInit {
  @ViewChild("myInput", { static: true }) input;
  ngOnInit(): void {
    console.log(this.input);
    const keyupEvents$ = fromEvent(this.input.nativeElement, "keyup");
    keyupEvents$.subscribe((event: Event) =>
      console.log((event.target as HTMLInputElement).value)
    );
  }
}
```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser
- Enter the letters `abcdef` into the input

```
a
ab
abc
abcd
...
```

<div style="page-break-after: always;"></div>

### Observers

**Observer**: is a collection of callbacks that knows how to listen to values delivered by the Observable.

```ts
import { Component, OnInit } from "@angular/core";
import { of, Observer } from "rxjs";

@Component({
  selector: "app-root",
  template: ``,
  styles: [],
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
    const observable$ = of(1, 2, 3);
    const observer: Observer<any> = {
      next: (x) => console.log(x),
      complete: () => console.log("completed"),
      error: (x) => console.log(x),
    };
    observable$.subscribe(observer);
  }
}
```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser

```
1
2
3
completed
...
```

<div style="page-break-after: always;"></div>

### Subcriptions

**Subscription**: represents the execution of an Observable, is primarily useful for cancelling the execution.

```diff
import { Component, OnInit } from '@angular/core';
import { of, Observer,
+ interval } from 'rxjs';

@Component({
  selector: 'app-root',
  template: ``,
  styles: []
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
-    const observable$ = of(1, 2, 3);
+    // Emits ascending numbers, one every second (1000ms)
+   const observable$ = interval(1000);
    const observer: Observer<any> = {
      next: x => console.log(x),
      complete: () => console.log('completed'),
      error: x => console.log(x)
    };
    const subscription = observable$.subscribe(observer);
+   setTimeout(() => subscription.unsubscribe(), 5000);
  }
}

```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser

```
0
1
2
3
4
...
```

<div style="page-break-after: always;"></div>

### Operators

Continue from prior demo or...

```shell
git checkout rxjs-subscriptions
```

#### map

```diff
import { Component, OnInit } from '@angular/core';
import { of, Observer, interval } from 'rxjs';
+ import { map } from 'rxjs/operators';

@Component({
  selector: 'app-root',
  template: ``,
  styles: []
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
    // Emits ascending numbers, one every second (1000ms)
    const observable$ = interval(1000);
    const observer: Observer<any> = {
      next: x => console.log(x),
      complete: () => console.log('completed'),
      error: x => console.log(x)
    };

+    const observableCommingOutOfThePipe$ = observable$.pipe(
+      map(x => x * 10)
+    );
+    const subscription = observableCommingOutOfThePipe$.subscribe(observer);

-   const subscription = observable$.subscribe(observer);
-   setTimeout(() => subscription.unsubscribe(), 5000);
  }
}

```

<div style="page-break-after: always;"></div>

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser

```
0
10
20
30
...
```

<div style="page-break-after: always;"></div>

#### tap

```diff
import { map,
+ tap } from 'rxjs/operators';
...

    const observableCommingOutOfThePipe$ = observable$.pipe(
+     tap(x => console.log(x)),
      map(x => x * 10)
    );
```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser

```
0
0
1
10
2
20
3
30
...
```

<div style="page-break-after: always;"></div>

#### filter

```ts
import { filter } from 'rxjs/operators';
...

const observableCommingOutOfThePipe$ = observable$.pipe(
  filter(x => x % 2 === 0)
);

```

Result

- Open Chrome DevTools
- Switch to the Console tab
- Refresh the browser

```
0
0
1
10
2
20
3
30
...
```

<div style="page-break-after: always;"></div>

RxJS code commonly uses the fluent syntax and chains functions.

```ts
ngOnInit(): void {
    // Emits ascending numbers, one every second (1000ms)
    // const observable$ = interval(1000);
    // const observer: Observer<any> = {
    //   next: x => console.log(x),
    //   complete: () => console.log('completed'),
    //   error: x => console.log(x)
    // };

    // const observableCommingOutOfThePipe$ = observable$.pipe(
    //   filter(x => x % 2 === 0)
    // );

    // observableCommingOutOfThePipe$.subscribe(observer);

    interval(1000)
      .pipe(filter(x => x % 2 === 0))
      .subscribe(x => console.log(x));
  }
```

<div style="page-break-after: always;"></div>

### Subjects

#### Read & Write

A Subject is like an Observable. It can be subscribed to, just like you normally would with Observables. It also has methods like next(), error() and complete() just like the observer you normally pass to your Observable creation function.

#### Multicast

The main reason to use Subjects is to multicast. An Observable by default is unicast. Unicasting means that each subscribed observer owns an independent execution of the Observable. To demonstrate this:

#### Unicast Observable Demo

```ts
import { Component, OnInit } from "@angular/core";
import { Observable } from "rxjs";

@Component({
  selector: "app-root",
  template: ``,
  styles: [],
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
    const observable = new Observable((subscriber) => {
      subscriber.next(Math.random());
    });

    // subscription 1
    observable.subscribe((data) => {
      console.log(data); // 0.24957144215097515 (random number)
    });

    // subscription 2
    observable.subscribe((data) => {
      console.log(data); // 0.004617340049055896 (random number)
    });
  }
}
```

#### Multicast

Subjects can multicast. Multicasting basically means that one Observable execution is shared among multiple subscribers.

_Subjects are like EventEmitters, they maintain a registry of many listeners._ When calling subscribe on a Subject it does not invoke a new execution that delivers data. It simply registers the given Observer in a list of Observers.

#### Multicast Subject Example

```ts
import { Component, OnInit } from "@angular/core";
import { Subject } from "rxjs";

@Component({
  selector: "app-root",
  template: ``,
  styles: [],
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
    const subject = new Subject();

    // subscription 1
    subject.subscribe((data) => {
      console.log(data); // 0.24957144215097515 (random number)
    });

    // subscription 2
    subject.subscribe((data) => {
      console.log(data); // 0.004617340049055896 (random number)
    });

    subject.next(Math.random());
  }
}
```

<div style="page-break-after: always;"></div>

###

Observables = data producers
Subjects = data producer and a data consumer

By using Subjects as a data consumer you can use them to convert Observables from unicast to multicast.

Here’s a demonstration of that:

```ts
import { Component, OnInit } from "@angular/core";
import { Subject, Observable } from "rxjs";

@Component({
  selector: "app-root",
  template: ``,
  styles: [],
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
    const observable = new Observable((subscriber) => {
      subscriber.next(Math.random());
    });

    const subject = new Subject();

    // subscriber 1
    subject.subscribe((data) => {
      console.log(data);
    });

    // subscriber 2
    subject.subscribe((data) => {
      console.log(data);
    });

    observable.subscribe(subject);
  }
}
```

### Practical Example

Search Box

```ts
import { Component, OnInit } from "@angular/core";
import { Subject } from "rxjs";

@Component({
  selector: "app-root",
  template: `
    <input
      type="text"
      #term
      (input)="search(term.value)"
      placeholder="search"
    />
    <br />
    <p *ngFor="let message of messages">{{ message }}</p>
  `,
  styles: [],
})
export class AppComponent implements OnInit {
  messages: string[] = [];
  private searchTermStream$ = new Subject<string>();

  ngOnInit(): void {
    this.searchTermStream$.subscribe((term) =>
      this.messages.push(`http call for: ${term}`)
    );
  }

  search(term: string) {
    this.searchTermStream$.next(term);
  }
}
```

<div style="page-break-after: always;"></div>

Result

- Type `angular` quickly in the searchbox
- Ouput is shown below the input on the page

```
http call for: an

http call for: ang

http call for: ang

http call for: angu

http call for: angular

http call for: angular

http call for: angular
...
```

<div style="page-break-after: always;"></div>

#### debounceTime

```diff
import { Component, OnInit } from '@angular/core';
import { Subject } from 'rxjs';
+ import { debounceTime } from 'rxjs/operators';

@Component({
  selector: 'app-root',
  template: `
    <input
      type="text"
      #term
      (keyup)="search(term.value)"
      placeholder="search"
    />
    <br />
    <p *ngFor="let message of messages">{{ message }}</p>
  `,
  styles: []
})
export class AppComponent implements OnInit {
  messages: string[] = [];
  private searchTermStream$ = new Subject<string>();

  ngOnInit(): void {
    this.searchTermStream$
+     .pipe(debounceTime(300))
      .subscribe(term => this.messages.push(`http call for: ${term}`));
  }

  search(term: string) {
    this.searchTermStream$.next(term);
  }
}
```

Result

- Type `angular` quickly in the searchbox
- Ouput is shown below the input on the page

```
http call for: angular
```

<div style="page-break-after: always;"></div>

#### distinctUntilChanged

Try

- Type `angular` quickly in the searchbox
- Delete the last letter `r` then retype the `r`
- Ouput is shown below the input on the page

Result

```
http call for: angular

http call for: angula

http call for: angular
```

<div style="page-break-after: always;"></div>

```diff
import { Component, OnInit } from '@angular/core';
import { Subject } from 'rxjs';
import { debounceTime,
+ distinctUntilChanged } from 'rxjs/operators';

@Component({
  selector: 'app-root',
  template: `
    <input
      type="text"
      #term
      (keyup)="search(term.value)"
      placeholder="search"
    />
    <br />
    <p *ngFor="let message of messages">{{ message }}</p>
  `,
  styles: []
})
export class AppComponent implements OnInit {
  messages: string[] = [];
  private searchTermStream$ = new Subject<string>();

  ngOnInit(): void {
    this.searchTermStream$
      .pipe(
+        debounceTime(1000),
+       distinctUntilChanged()
      )
      .subscribe(term => this.messages.push(`http call for: ${term}`));
  }

  search(term: string) {
    this.searchTermStream$.next(term);
  }
}
```

<div style="page-break-after: always;"></div>

Try

- Type `angular` quickly in the searchbox
- Delete the last letter `r` then retype the `r`
- Ouput is shown below the input on the page

Result

```
http call for: angular
```

Notice that I increased the debounceTime so that it's easier to retype the letters you removed.

<div style="page-break-after: always;"></div>

#### switchMap

Cancels the orginal obervable and returns a new one

```diff
this.searchTermStream$
      .pipe(
        debounceTime(1000),
        distinctUntilChanged(),
+        switchMap((term: string) => {
+          return of(`new observable: ${term}`);
+        })
      )
      .subscribe(term => this.messages.push(` ${term}`));
```

<div style="page-break-after: always;"></div>

## Additional Reading

- [Understanding RxJS BehaviorSubject, ReplaySubject and AsyncSubject](https://medium.com/@luukgruijs/understanding-rxjs-behaviorsubject-replaysubject-and-asyncsubject-8cc061f1cfc0)
- [Persist Login Status with Behavior Subject](https://netbasal.com/angular-2-persist-your-login-status-with-behaviorsubject-45da9ec43243)

<div style="page-break-after: always;"></div>

## Http

### Get

- Checkout start branch

```shell
git checkout http-start
```

Which has db.json, api script, and json-server installed

- Create model

```shell
ng g class photo
```

Rename `photo.ts` to `photo.model.ts`

```ts
export class Photo {
  id: number = 0;
  title?: string | null;
  url?: string | null;
  thumbnailUrl?: string | null;
}
```

- Create service

```shell
ng g service photo
```

- Import HttpClientModule

```diff
// app.module.ts
...
+ import { HttpClientModule } from '@angular/common/http';
@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule,
+    HttpClientModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

<div style="page-break-after: always;"></div>

- Inject HttpClient service
- Implement getAll method

```diff
import { Injectable } from '@angular/core';
+ import { HttpClient } from '@angular/common/http';
+ import { Photo } from './photo.model';
+ import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class PhotoService {
+  constructor(private http: HttpClient) {}

+  getAll(): Observable<Photo[]> {
+    return this.http.get<Photo[]>('http://localhost:3000/photos');
+  }
}
```

```ts
// app.component.ts
import { Component, OnInit } from "@angular/core";
import { PhotoService } from "./photo.service";

@Component({
  selector: "app-root",
  template: `
    <h1>Photos</h1>
    <div *ngFor="let photo of photos">
      <img [src]="photo.thumbnailUrl" [alt]="photo.title" />
      <p>{{ photo.title }}</p>
    </div>
  `,
  styles: [],
})
export class AppComponent implements OnInit {
  photos: Photo[] = [];
  constructor(private photoService: PhotoService) {}
  ngOnInit(): void {
    this.photoService.getAll().subscribe((data) => (this.photos = data));
  }
}
```

<div style="page-break-after: always;"></div>

### Error Handling

#### `photo.service.ts`

```ts
import { HttpClient, HttpErrorResponse } from "@angular/common/http";
import { Injectable } from "@angular/core";
import { Observable, throwError } from "rxjs";
import { Photo } from "./photo";
import { catchError } from "rxjs/operators";

@Injectable({
  providedIn: "root",
})
export class PhotoService {
  constructor(private http: HttpClient) {}

  getAll(): Observable<Photo[]> {
    return this.http.get<Photo[]>("http://localhost:3000/photos/wrong").pipe(
      catchError((error: HttpErrorResponse) => {
        console.log(error);
        return throwError("An error occured loading the photos.");
      })
    );
  }
}
```

#### `app.component.ts`

```ts
import { OnInit } from "@angular/core";
import { Component } from "@angular/core";
import { Photo } from "./photo";
import { PhotoService } from "./photo.service";

@Component({
  selector: "app-root",
  template: `
    <h1>Photos</h1>
    <p *ngIf="errorMessage">{{ errorMessage }}</p>
    <div *ngFor="let photo of photos">
      <img [src]="photo.thumbnailUrl" [alt]="photo.title" />
      <p>{{ photo.title }}</p>
    </div>
  `,
  styles: [],
})
export class AppComponent implements OnInit {
  photos: Photo[] = [];
  errorMessage?: string | null;
  constructor(private photoService: PhotoService) {}
  ngOnInit(): void {
    this.photoService.getAll().subscribe(
      (data) => (this.photos = data),
      (error) => (this.errorMessage = error)
    );
  }
}
```

### Retry

```
git checkout http-retry -f
```

```ts
// see photo.service.ts
```

<!-- ### Put, Post, Delete -->

<div style="page-break-after: always;"></div>

## Routing

### Routing Basics

- Start Server

```shell
ng serve -o
```

- Generate Components

```shell
ng g component home
ng g component about
ng g component contact
```

- Add Routes
  - Snippets
    - a-route-path-eager
    - a-route-path-default

```
const routes: Routes = [
  { path: '', pathMatch: 'full', redirectTo: 'home' },
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: 'contact', component: ContactComponent },
];
```

- Add Navigation and the `router-outlet`

#### `app.component.ts`

```html
<nav>
  <a [routerLink]="['/home']">Home</a> |
  <a [routerLink]="['/about']">About</a> |
  <a [routerLink]="['/contact']">Contact</a>
</nav>
<router-outlet></router-outlet>
```

- Highlight Active Navigation Item

```html
<nav>
  <a routerLinkActive="active" [routerLink]="['/home']">Home</a> |
  <a routerLinkActive="active" [routerLink]="['/about']">About</a> |
  <a routerLinkActive="active" [routerLink]="['/contact']">Contact</a>
</nav>
<router-outlet></router-outlet>
```

<!-- <div style="page-break-after: always;"></div> -->

### Routing Navigation

- Start with routing-navigation-start branch as shown below.
- Merge the service branch.

```shell
git checkout routing-navigation-start
```

#### Code Review

All the steps in this next section have already been completed so just review/walkthrough the existing code before moving to the next section.

- Create a movies module.

```shell
ng g module movies --routing --module=app
```

- Create a movie model class.

```shell
ng g class movies/shared/movie
```

1. Rename file `movie.ts` to `movie.model.ts`.
2. Add properties to the movie model.

```ts
export class Movie {
  constructor(
    public id: number,
    public name: string,
    public description: string
  ) {}
}
```

<div style="page-break-after: always;"></div>

- Create mock movie data.
  1. Create file `movies/shared/mock-movies.ts`
  2. Add these movies.

```ts
import { Movie } from "./movie.model";

export const MOVIES: Movie[] = [
  new Movie(
    1,
    " Titanic",
    "A seventeen-year-old aristocrat falls in love with a kind but poor artist aboard the luxurious, ill-fated R.M.S. Titanic."
  ),
  new Movie(
    2,
    " E.T. the Extra-Terrestrial",
    "A troubled child summons the courage to help a friendly alien escape Earth and return to his home world."
  ),
  new Movie(
    3,
    "The Wizard of Oz",
    "Dorothy Gale is swept away from a farm in Kansas to a magical land of Oz in a tornado and embarks on a quest with her new friends to see the Wizard who can help her return home in Kansas and help her friends as well."
  ),
  new Movie(
    4,
    "Star Wars: Episode IV - A New Hope ",
    "Luke Skywalker joins forces with a Jedi Knight, a cocky pilot, a Wookiee and two droids to save the galaxy from the Empire/`s world-destroying battle-station while also attempting to rescue Princess Leia from the evil Darth Vader."
  ),
];
```

<div style="page-break-after: always;"></div>

- Create a movie service.
  ```shell
  ng g service movies/shared/movie
  ```
- Add find and list methods and bring in the needed imports.

`movies\shared\movie.service.ts`

```ts
import { of } from "rxjs";
import { Observable } from "rxjs";
import { Injectable } from "@angular/core";

@Injectable()
export class MovieService {
  list(): Observable<Movie[]> {
    return of(MOVIES);
  }

  find(id: number): Observable<Movie> {
    const movie = MOVIES.find((m) => m.id === id);
    return of(movie);
  }
}
```

<div style="page-break-after: always;"></div>

- Also review the movie components code for the list and detail.

  - list
  - detail

These components were generated with the following commands:

```shell
ng g component movies/movie-list
```

```shell
ng g component movies/movie-detail
```

<div style="page-break-after: always;"></div>

#### Routing Changes

The steps from here are changes that should be made to the code.

```diff
//movies/movie-list/movie-list.component.ts

import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-movie-list',
  template: `
  <div>
  <ul>
      <li *ngFor="let movie of movies" >
          <a
+          [routerLink]="['detail', movie.id]">
          {{movie.name}}
          </a>
      </li>
  </ul>
  </div>
  `,
  styles: []
})
export class MovieListComponent implements OnInit {
  movies: Movie[];

  constructor(private movieService: MovieService) {}

  ngOnInit() {
    this.movieService.list().subscribe(data => (this.movies = data));
  }
}
```

<div style="page-break-after: always;"></div>

- detail

```diff
//movies/movie-detail/movie-detail.component.ts
...
+ import { MovieService } from '../shared/movie.service';
+ import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-movie-detail',
  template: `
    <div *ngIf="movie">
      <h5>{{ movie.name }}</h5>
      <p>{{ movie.description }}</p>
    </div>
  `,
  styles: []
})
export class MovieDetailComponent implements OnInit {
  movie: Movie;

  constructor(
+    private movieService: MovieService,
+    private route: ActivatedRoute
  ) {}

+  ngOnInit() {
+    this.route.paramMap.subscribe(params => {
+      const id = parseInt(params.get('id'), 10);
+      this.movieService.find(id).subscribe(m => (this.movie = m));
+    });
  }
  }
}
```

<div style="page-break-after: always;"></div>

- Configure routes.

```diff
//movies/movies-routing.module.ts
const routes: Routes = [
  { path: 'movies',component: MovieListComponent},
+ { path: 'movies/detail/:id', component: MovieDetailComponent }
];
```

- Add Navigation Item
  ```diff
  <nav>
  <a routerLinkActive="active" [routerLink]="['/home']">Home</a> |
  <a routerLinkActive="active" [routerLink]="['/about']">About</a> |
  <a routerLinkActive="active" [routerLink]="['/contact']">Contact</a> |
  +  <a routerLinkActive="active" [routerLink]="['/movies']">Movies</a>
  </nav>
  ```

<div style="page-break-after: always;"></div>

## Routing (Advanced)

### Child Routes

Continue from the previous code (routing-navigation).

- Configure child routes.

```diff
// movies/movies-routing.module.ts
const routes: Routes = [
  {
    path: 'movies',
    component: MovieListComponent
+  children: [{ path: 'detail/:id', component: MovieDetailComponent }]
  },
-  { path: 'movies/detail/:id', component: MovieDetailComponent }
];
```

- Add an outlet

```diff
// movies/movie-list/movie-list.component.ts
@Component({
  selector: 'app-movie-list',
  template: `
  <div>
  <ul>
      <li *ngFor="let movie of movies" >
          <a [routerLink]="['detail', movie.id]">{{movie.name}}</a>
      </li>
  </ul>
  </div>
+  <div>
+    <router-outlet></router-outlet>
+  </div>
  `,
  styles: []
})
export class MovieListComponent implements OnInit {
...
```

<div style="page-break-after: always;"></div>

### Lazy Loading

- Configure Movies Module to lazy load.

> It can be useful to look at the size of `main.js` in the Chrome DevTools Network tab and record it on the board before doing this demonstration. Be sure to clear the browser cache so you get the correct file size. You can then repeat the process at the end of the lab and show that the file size is about half of the original size.

Continue from the code from the previous step (routing-navigation).

> Be sure to remove the child route and go back to a traditional route as shown in the step below or other code would need to be adjusted to demonstrate lazy-loading.

```diff
// movies/movies-routing.module.ts
const routes: Routes = [
  {
-    path: 'movies'
+    path: '',
    component: MovieListComponent,
+    children: [{ path: 'detail/:id', component: MovieDetailComponent }]
  }
-  // { path: 'movies/detail/:id', component: MovieDetailComponent }
];
```

```diff
// app.module.ts

  imports: [
    BrowserModule,
    AppRoutingModule,
-   MoviesModule
  ],
```

<div style="page-break-after: always;"></div>

```diff
// app-routing.module.ts
const routes: Routes = [
  { path: '', pathMatch: 'full', redirectTo: 'home' },
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: 'contact', component: ContactComponent },
+  {
+    path: 'movies',
+    loadChildren: () => import('../app/movies/movies.module').then(m => m.MoviesModule)
+  }
];
```

> Note the `import` syntax shown above is new as of Angular 8. For older versions use: `loadChildren: '../app/movies/movies.module#MoviesModule'`. The older "string" syntax will not work in Angular version 9 or higher because it was removed in that version.

<div style="page-break-after: always;"></div>

## Components (Advanced)

### Change Detection

#### Checkout

```shell
git checkout change-detection -f
```

The following components are already created.

```shell
parent
child-a
child-b
grandchild-a
```

<div style="page-break-after: always;"></div>

#### ChangeDetectionStrategy.Default

Click on each of the buttons to see what components are checked by change detection.
Refreshing the page after each button click makes this easier to see.

- If an input "changes" (clicking the parent button which sets the nickname) then the entire tree is checked.
- If an event triggered then the entire tree is checked.

#### ChangeDetectionStrategy.OnPush

Go into each of the following child components.

- child-a
- child-b
- grandchild-a

Uncomment the line to modify the change detection strategy from:

- the default aptly named `ChangeDetectionStrategy.Default`
- to `ChangeDetectionStrategy.OnPush`

Click on each of the buttons to see what components are checked by change detection.
Refreshing the page after each button click makes this easier to see.

- If a component has a changed input or raises an event, causes check on itself (component) and all ancestors
  - If an input "changes" then checks itself (component with input) and all ancestors
  - If an event happens then checks itself (component where event was raised, Ex. click) and all ancestors

<!-- ### Lifecycle Hooks -->

<div style="page-break-after: always;"></div>

<!-- ## Http Advanced ### Retry ### Cache### Interceptors -->

<div style="page-break-after: always;"></div>

# Appendixes

Optional demos if class requests and time permits.

## Redux (NgRx)

### Redux (NgRx) Counter

Documentation available at:
https://ngrx.io/

#### Setup

1. Open: `demos\start`
1. Run `npm install` if you haven't earlier in the class.

#### Installation

1. Install @ngrx/schematics from npm:

   ```
   ng add @ngrx/schematics
   ```

1. This will ask you if you want to make the @ngrx/schematics the default collection in your Angular CLI project. Choose `n` for no in this demo.

   > NgRx Schematics helps you avoid writing common boilerplate and instead focus on building your application
   > The @ngrx/schematics command prefix is only needed when the default collection isn't set. For example, the command `ng g @ngrx/schematics:action Counter` could just be `ng g action Counter`

1. After installing @ngrx/schematics, install the NgRx dependencies.

   ```
   ng add @ngrx/store
   ng add @ngrx/store-devtools
   ```

   In more complex applications, you may also want to install the follow NgRx libraries but there is no need to run the below commands in this example.

   ```
   # DO NOT RUN THESE COMMANDS
   npm add @ngrx/effects
   npm add @ngrx/entity
   ```

<div style="page-break-after: always;"></div>

#### Store

Generate the initial state management and register it within the app.module.ts

```
ng generate @ngrx/schematics:store State --root --module app.module.ts
```

> If this command doesn't work try adding `ng add @ngrx/schematics` again.

> By adding the StoreModule.forRoot function in the imports array of your AppModule. The StoreModule.forRoot() method registers the global providers needed to access the Store throughout your application.

#### Actions

Create actions.

1. Create the directories `src\app\counter\` and `src\app\counter\shared`.
2. Create a file named `src\app\counter\shared\counter.actions.ts`

3. Describe the counter actions to increment, decrement, and reset its value.

```ts
// src\app\counter\shared\counter.actions.ts
import { createAction } from "@ngrx/store";

export const increment = createAction("[Counter] Increment");
export const decrement = createAction("[Counter] Decrement");
export const reset = createAction("[Counter] Reset");
```

<div style="page-break-after: always;"></div>

#### Reducer

Create a reducer.

1. Create a file named `src\app\counter\shared\counter.reducer.ts`

   Define a reducer function to handle changes in the counter value based on the provided actions.

   ```ts
   // src\app\counter\shared\counter.reducer.ts
   import { createReducer, on } from "@ngrx/store";
   import { increment, decrement, reset } from "./counter.actions";

   export const initialState = 0;

   const _counterReducer = createReducer(
     initialState,
     on(increment, (state) => state + 1),
     on(decrement, (state) => state - 1),
     on(reset, (state) => 0)
   );

   export function counterReducer(state, action) {
     return _counterReducer(state, action);
   }
   ```

    <div style="page-break-after: always;"></div>

1. Add the count to the state interface and the reducers object and set the counterReducer to manage the state of the counter.

   ```diff
   // src/app/reducers/index.ts

   import {
   ActionReducer,
   ActionReducerMap,
   createFeatureSelector,
   createSelector,
   MetaReducer
   } from '@ngrx/store';
   import { environment } from '../../environments/environment';
   + import { counterReducer } from '../counter/shared/counter.reducer';

   export interface State {
   +  count: number;
   }

   export const reducers: ActionReducerMap<State> = {
   +   count: counterReducer
   };

   export const metaReducers: MetaReducer<State>[] = !environment.production
   ? []
   : [];
   ```

    <div style="page-break-after: always;"></div>

#### User Interface

1. Generate a counter module.

   ```
   ng g m counter --module=app
   ```

1. Generate a component to display the counter.

   ```shell
   ng generate component counter/my-counter
   ```

1. Update the `MyCounterComponent` class with a selector for the `count`, and methods to dispatch the Increment, Decrement, and Reset actions.
1. Then update the `MyCounterComponent` template with buttons to call the increment, decrement, and reset methods. Use the async pipe to subscribe to the count\$ observable.

   ```diff
   // src/app/counter/my-counter/my-counter.component.ts
   import { Component, OnInit
   + , ChangeDetectionStrategy
    } from '@angular/core';
   import { Store,
   + select
   } from '@ngrx/store';
   + import { Observable } from 'rxjs';
   + import { increment, decrement, reset } from '../shared/counter.actions';

   @Component({
   selector: 'app-my-counter',
   template: `
   +    <button (click)="increment()">Increment</button>
   +
   +    <div>Current Count: {{ count$ | async }}</div>
   +
   +    <button (click)="decrement()">Decrement</button>
   +
   +   <button (click)="reset()">Reset Counter</button>
   `,
   +  changeDetection: ChangeDetectionStrategy.OnPush,
   styles: []
   })
   export class MyCounterComponent {
   +  count$: Observable<number>;

   +  constructor(private store: Store<{ count: number }>) {
   +    this.count$ = store.pipe(select('count'));
   +  }

   +  increment() {
   +    this.store.dispatch(increment());
   +  }

   +  decrement() {
   +    this.store.dispatch(decrement());
   +  }

   +  reset() {
   +    this.store.dispatch(reset());
   +  }
   }

   ```

1. Export the `MyCounterComponent` from the `CounterModule`.

   ```diff
   import { NgModule } from '@angular/core';
   import { CommonModule } from '@angular/common';
   import { MyCounterComponent } from './my-counter/my-counter.component';

   @NgModule({
   declarations: [MyCounterComponent],
   imports: [CommonModule],
   +  exports: [MyCounterComponent]
   })
   export class CounterModule {}
   ```

1. Add the `MyCounterComponent` to your `AppComponent` template.

   ```diff
   import { Component } from '@angular/core';

   @Component({
   selector: 'app-root',
   template: `
   +    <app-my-counter></app-my-counter>
   `,
   styles: []
   })
   export class AppComponent {}
   ```

1. If not already running start the application with the following command:

   ```shell
   ng serve -o
   ```

1. Open `Chrome DevTools` and demonstrate the time traveling, record replay, and logging features of the `Redux DevTools` extension.

   > Directions on installing this extension included as part of the setup document for the class.

Finished code available in `demos\ngrx-counter1`.

<div style="page-break-after: always;"></div>

<div style="page-break-after: always;"></div>

### NgRx Lab

#### Setup

1. This lab is designed to be done starting with the completed code from `lab29`. If your code is at that point then continue to the next step. If your code is not at that point, then **checkout** the branch `lab29` as detailed in the steps below.

   ```
   # open a powershell or terminal window
   # cd into your `working` directory where you are coding in this class
   git clone https://github.com/craigmckeachie/a16_labs project-manage
   cd project-manage
   git checkout lab29
   npm install
   # open `project-manage` in VS Code
   # open a powershell or terminal window and `cd` to `project-manage`
   ng serve -o
   # Optional: name this terminal window `web`
   # open another (new) powershell or terminal window and `cd` to `project-manage`
   npm run api
   # Optional: name this terminal window `api`
   ```

#### Installation

1. **Install** `@ngrx/schematics` from npm:

   ```
   ng add @ngrx/schematics
   ```

1. This will ask you if you want to make the `@ngrx/schematics` the **default** **collection** in your Angular CLI project. **Choose** `n` for **no** in this lab.

1. After installing @ngrx/schematics, **install** the NgRx **following** **library** dependencies.

   > After each of these commands you will be asked if you want to install the corresponding package. Answer 'Y' for yes.

   ```
   ng add @ngrx/store
   ng add @ngrx/store-devtools
   ng add @ngrx/effects
   ```

1. Generate the initial state management and register it within the app.module.ts

   ```
   ng generate @ngrx/schematics:store State --root --module app.module.ts
   ```

1. Generate the root effects and register it with the app.module.ts
   ```
   ng generate @ngrx/schematics:effect App --root --module app.module.ts
   ```
   > - Should we wire up success and failure actions? No
   > - Do you want to use the create function? Yes
1. **Open** `src\app\app.module.ts` and notice that the `StoreModule` was automatically imported by the `ng add` commands and the Redux Dev Tools are configured.

<div style="page-break-after: always;"></div>

#### Actions

1. **Create** the `src\app\projects\shared\state` **directories**.
2. **Create** the **file** `src\app\projects\shared\state\project.actions.ts`.
3. **Add** the following **actions** using the `createAction` helper function.

   `src\app\projects\shared\state\project.actions.ts`

   ```ts
   import { createAction, props } from "@ngrx/store";
   import { Project } from "../project.model";

   export const load = createAction("[Project] Load");
   export const loadSuccess = createAction(
     "[Project] Load Success",
     props<{ projects: Project[] }>()
   );
   export const loadFail = createAction(
     "[Project] Load Fail",
     props<{ error: any }>()
   );

   export const save = createAction(
     "[Project] Save",
     props<{ project: Project }>()
   );
   export const saveSuccess = createAction(
     "[Project] Save Success",
     props<{ project: Project }>()
   );
   export const saveFail = createAction(
     "[Project] Save Fail",
     props<{ error: any }>()
   );
   ```

<div style="page-break-after: always;"></div>

#### State

1. **Create** the **file** `src\app\projects\shared\state\project.reducer.ts`.
2. Define the state for the slice of the state related to projects including:

   1. an interface
   2. initial or default values
   3. selectors to select different parts of state

   **`src\app\projects\shared\state\project.reducer.ts`**

   ```ts
   import { Project } from "../project.model";
   import { State } from "src/app/reducers";

   export interface ProjectState {
     loading: boolean;
     saving: boolean;
     error: string;
     projects: Project[];
   }

   export const initialState: ProjectState = {
     loading: false,
     saving: false,
     error: "",
     projects: [],
   };

   export const getProjects = (state: State) => state.projectState.projects;
   export const getLoading = (state: State) => state.projectState.loading;
   export const getSaving = (state: State) => state.projectState.saving;
   export const getError = (state: State) => state.projectState.error;
   ```

   > ! At this point, you will see the following error

   ```
   Property 'projectState' does not exist on type 'State'.ts
   ```

   > You can safely ignore as we will resolve it in a later step.

<div style="page-break-after: always;"></div>

#### Reducer

1. Create the `projectReducer` using the `createReducer` helper function.

**`src\app\projects\shared\state\project.reducer.ts`**

```ts
... // add this code to the code in the last step

import { createReducer, on } from '@ngrx/store';
import {
  load,
  loadSuccess,
  loadFail,
  save,
  saveSuccess,
  saveFail,
} from './project.actions';

export const projectReducer = createReducer(
  initialState,
  on(load, (state) => ({ ...state, loading: true })),
  on(loadSuccess, (state, { projects }) => ({
    ...state,
    projects,
    loading: false,
    saving: false,
  })),
  on(loadFail, (state, { error }) => ({ ...state, error, loading: false })),
  on(save, (state) => ({ ...state, saving: true })),
  on(saveSuccess, (state, { project }) => {
    const updatedProjects = state.projects.map((item) =>
      project.id === item.id ? project : item
    );
    return {
      ...state,
      projects: updatedProjects,
      saving: false,
    };
  }),
  on(saveFail, (state, { error }) => ({ ...state, error, saving: false }))
);

```

<div style="page-break-after: always;"></div>

#### Effects

1. Create the `ProjectEffects` class and the `load$` and `save$` effects using the `createEffect` helper function.

   **`src\app\projects\shared\state\project.effects.ts`.**

   ```ts
   import { Injectable } from "@angular/core";
   import { of } from "rxjs";
   import { Actions, ofType, createEffect } from "@ngrx/effects";

   import { switchMap, catchError, map, mergeMap } from "rxjs/operators";
   import { ProjectService } from "../project.service";
   import {
     load,
     loadSuccess,
     loadFail,
     save,
     saveSuccess,
     saveFail,
   } from "./project.actions";

   @Injectable()
   export class ProjectEffects {
     load$ = createEffect(() => {
       return this.actions$.pipe(
         ofType(load),
         switchMap(() => {
           return this.projectService.list().pipe(
             map((data) => loadSuccess({ projects: data })),
             catchError((error) => of(loadFail({ error: error })))
           );
         })
       );
     });

     save$ = createEffect(() => {
       return this.actions$.pipe(
         ofType(save),
         mergeMap(({ project }) => {
           return this.projectService.put(project).pipe(
             map(() => saveSuccess({ project })),
             catchError((error) => of(saveFail({ error: error })))
           );
         })
       );
     });

     constructor(
       private actions$: Actions,
       private projectService: ProjectService
     ) {}
   }
   ```

<div style="page-break-after: always;"></div>

#### Configure

1. Add the project related state and reducer to the root state and reducer.

   **`src\app\reducers\index.ts`.**

   ```diff
   import {
   ActionReducer,
   ActionReducerMap,
   createFeatureSelector,
   createSelector,
   MetaReducer
   } from '@ngrx/store';
   import { environment } from '../../environments/environment';
   + import {
   +   ProjectState,
   +   projectReducer
   + } from '../projects/shared/state/project.reducer';

   export interface State {
   +  projectState: ProjectState;
   }

   export const reducers: ActionReducerMap<State> = {
   +  projectState: projectReducer
   };

   export const metaReducers: MetaReducer<State>[] = !environment.production
   ? []
   : [];
   ```

<div style="page-break-after: always;"></div>

#### Connect the Container & Store

1. Refactor the `ProjectsContainerComponent` to use the `Store` instead of the `ProjectService` to access data. More specifically:

   1. Change all class members to be Observables.
   2. Inject the `Store` instead of the `ProjectService` in the component's constructor.
   3. Dispatch the `load` action in `ngOnInit` instead of calling the service directly.
   4. Dispatch the `save` action in the `onSaveListItem` event handler method instead of calling the service directly.

   **`src\app\projects\projects-container\projects-container.component.ts`**

   ```diff
   import { Component, OnInit
   + , ChangeDetectionStrategy
    } from '@angular/core';
   import { Project } from '../shared/project.model';
   - import { ProjectService } from '../shared/project.service';
   + import { Observable } from 'rxjs';
   + import { Store, select } from '@ngrx/store';
   + import { State } from 'src/app/reducers';
   + import { load, save } from '../shared/state/project.actions';
   + import {
   +   getProjects,
   +   getError,
   +   getLoading,
   +   getSaving
   + } from '../shared/state/project.reducer';

   @Component({
   selector: 'app-projects-container',
   templateUrl: './projects-container.component.html',
   styleUrls: ['./projects-container.component.css'],
   + changeDetection: ChangeDetectionStrategy.OnPush
   })
   export class ProjectsContainerComponent implements OnInit {
   -  projects: Project[];
   -  errorMessage: string;
   -  loading: boolean;
   +  projects$!: Observable<Project[]>;
   +  errorMessage$!: Observable<string>;
   +  loading$!: Observable<boolean>;
   +  saving$!: Observable<boolean>;

   -  constructor(private projectService: ProjectService) {}
   +  constructor(private store: Store<State>) {}

   ngOnInit() {
   -    this.loading = true;
   -    this.projectService.list().subscribe(
   -      data => {
   -        this.loading = false;
   -        this.projects = data;
   -      },
   -      error => {
   -        this.loading = false;
   -        this.errorMessage = error;
   -      }
   -    );
   +    this.projects$ = this.store.pipe(select(getProjects));
   +    this.errorMessage$ = this.store.pipe(select(getError));
   +    this.loading$ = this.store.pipe(select(getLoading));
   +    this.saving$ = this.store.pipe(select(getSaving));
   +    this.store.dispatch(load());
   }

   onSaveListItem(event: any) {
       const project: Project = event.item;
   -    this.projectService.put(project).subscribe(
   -      updatedProject => {
   -        const index = this.projects.findIndex(
   -          element => element.id === project.id
   -        );
   -        this.projects[index] = project;
   -      },
   -      error => (this.errorMessage = error)
   -    );
   -  }
   +   this.store.dispatch(save({ project }));

   }

   ```

    <div style="page-break-after: always;"></div>

**`src\app\projects\projects-container\projects-container.component.html`**

```html
<h1>Projects</h1>
<div *ngIf="loading$ | async" class="center-page">
  <span class="spinner primary"></span>
  <p>Loading...</p>
</div>
<span *ngIf="saving$ | async" class="toast"> Saving... </span>
<div class="row">
  <div *ngIf="errorMessage$ | async as errorMessage" class="card large error">
    <section>
      <p><span class="icon-alert inverse"></span> {{ errorMessage }}</p>
    </section>
  </div>
</div>
<ng-container *ngIf="projects$ | async as projects">
  <app-project-list
    [projects]="projects"
    (saveListItem)="onSaveListItem($event)"
  >
  </app-project-list>
</ng-container>
```

1. Register the `ProjectEffects`.

   **`src\app\app.module.ts`**

```diff
+ import { ProjectEffects } from './projects/shared/state/project.effects';

@NgModule({
  declarations: [AppComponent],
  imports: [
    BrowserModule,
    AppRoutingModule,
    ProjectsModule,
    HttpClientModule,
    HomeModule,
    StoreModule.forRoot(reducers, {
      metaReducers
    }),
    StoreDevtoolsModule.instrument({
      maxAge: 25,
      logOnly: environment.production
    }),
+   EffectsModule.forRoot([AppEffects,
+   ProjectEffects])
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

1. Verify the application functionality works as it did previously including:
   1. Loading and saving data.
   2. Handles errors appropriately when the backend is down.
   3. Displays loading and saving messages.
1. Lastly, verify you can now time travel.
   1. Open Chrome DevTools (F12 or fn+F12 on Windows)
   1. Install the [Redux DevTools Extension](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en) if you haven't already.
   1. Use the application and then travel back in time and replay your actions.

<div style="page-break-after: always;"></div>

### NgRx Resources

- [Official Documentation](https://ngrx.io/)
- [Example Application](https://github.com/ngrx/platform/tree/master/projects/example-app)
- [New Features in NgRx 8](https://medium.com/ngrx/announcing-ngrx-version-8-ngrx-data-create-functions-runtime-checks-and-mock-selectors-a44fac112627)
- [NgRx Resources](https://ngrx.io/resources)

  #### Online courses

  Pluralsight (Deborah Kurata and Duncan Hunter)
  [Angular NgRx: Getting Started](https://www.pluralsight.com/courses/angular-ngrx-getting-started)

  [Ultimate Angular (Todd Motto)
  NGRX Store + Effects](https://ultimatecourses.com/learn/ngrx-store-effects)

  #### Redux & GraphQL Resources

  [GraphQL](https://graphql.org/)

  [How GraphQL Replaces Redux](https://hackernoon.com/how-graphql-replaces-redux-3fff8289221d)

  [Free Video Course on Redux by Creator](https://egghead.io/courses/getting-started-with-redux)

  [Future: Less State Management](https://medium.com/@amcdnl/the-future-of-javascript-state-management-is-less-state-management-ba1d97b99308)

  [You Might Not Need Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367)

  [Presentational vs Container components divide](https://twitter.com/dan_abramov/status/802569801906475008)

<div style="page-break-after: always;"></div>

## Template-driven Forms

### Template Forms Binding

```diff
// app.module.ts
+ import { FormsModule } from '@angular/forms';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule,
+           FormsModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

```ts
// app.component.ts
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `
    <form #signinForm="ngForm" (submit)="onSubmit(signinForm)">
      <input type="text" ngModel name="username" placeholder="username" /><br />
      <input type="text" ngModel name="password" placeholder="password" /><br />
      <button>Sign In</button>
    </form>
    <pre>
      {{ signinForm.value | json }}
    </pre
    >
  `,
  styles: [],
})
export class AppComponent {
  onSubmit(form) {
    console.log(form.value);
  }
}
```

<div style="page-break-after: always;"></div>

### Template Forms Validation

```diff
// app.component.ts

import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
  <form #signinForm="ngForm" (submit)="onSubmit(signinForm)">
      <input
        type="text"
        placeholder="username"
        ngModel
+        #username="ngModel"
        name="username"
+        required
+        minlength="3"
      /><br />
+      <pre>
+        {{ username.errors | json }}
+      </pre
      >
+      <br />
+      Dirty: {{ username.dirty | json }} <br />
+      Touched: {{ username.touched | json }} <br />
      <input type="text" ngModel name="password" placeholder="password" /><br />
      <button>Sign In</button>
    </form>
  `,
  styles: []
})
export class AppComponent {
  ...
}
```

<div style="page-break-after: always;"></div>

#### Displaying Validation Messages

```diff
// app.component.ts

@Component({
  selector: 'app-root',
  template: `
    <form #signinForm="ngForm" (submit)="onSubmit(signinForm)">
      <input
        type="text"
        placeholder="username"
        ngModel
        #username="ngModel"
        name="username"
        required
        minlength="3"
      /><br />
+      <div *ngIf="username.hasError('required') && username.dirty">
+        Username is required.
+      </div>

-      <pre>
-        {{ username.errors | json }}
-      </pre>
-      <br />
-      Dirty: {{ username.dirty | json }} <br />
-      Touched: {{ username.touched | json }} <br />
      <input type="text" ngModel name="password" placeholder="password" /><br />

      <button>Sign In</button>
    </form>
  `,
  styles: []
})
export class AppComponent {
...
}
```

<div style="page-break-after: always;"></div>

### Two-way Binding

```ts
@Component({
  selector: "app-root",
  template: `
    <input
      [value]="message"
      (input)="message = $event.target.value"
      type="text"
    />
    <p>{{ message }}</p>
  `,
  styles: [],
})
export class AppComponent {
  message = "";
}
```

```ts
import { FormsModule } from "@angular/forms";

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, AppRoutingModule, FormsModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

```ts
@Component({
  selector: "app-root",
  template: `
    <input [(ngModel)]="message" type="text" />
    <p>{{ message }}</p>
  `,
  styles: [],
})
export class AppComponent {
  message = "";
}
```

<div style="page-break-after: always;"></div>

## Angular Material: Introduction

### Installation

1. In a command-prompt (Windows) or terminal (Mac) run the following commands.

   ```shell
   ng new my-mat-proj
   cd my-mat-proj
   ng add @angular/material
   code .
   ```

   Choose:

   - indigo-pink.css
   - HammerJS: Yes
   - Browser animations: Y

1. Open `my-mat-proj` in your editor.

   ```shell
   code .
   ```

1. Look at the changes using a Git diff.

> What the command does:

        - Ensure project dependencies are placed in package.json
        - Enable the BrowserAnimationsModule your app module
        - Add either a prebuilt theme or a custom theme
        - Add Roboto fonts to your index.html
        - Add the Material Icon font to your index.html
        - Add global styles to
        - Remove margins from body
        - Set height: 100% on html and body
        - Make Roboto the default font of your app
        - Install and import hammerjs for gesture support in your project

<div style="page-break-after: always;"></div>

3. Add a slider.

   `src\app\app.module.ts`

   ```ts
   import { MatSliderModule } from '@angular/material/slider';
   …
   @NgModule ({....
     imports: [...,
     MatSliderModule,
   …]
   })
   ```

   `src\app\app.component.html`

   ```html
   // delete contents
   <mat-slider min="1" max="100" step="1" value="1"></mat-slider>
   ```

4. Build and run the application.

   ```shell
   ng serve
   ```

<div style="page-break-after: always;"></div>

### Navigation

1. Generate a navigation component.

   ```shell
   ng generate @angular/material:nav mainnav
   ```

2. Add the component to the main content area.

   `src/app/mainnav/mainnav.component.html`

   ```diff
   </mat-toolbar>
       <!-- Add Content Here -->
   +    <h1>Main Content</h1>
   +    <p>This is the main content</p>
     </mat-sidenav-content>
   ```

   > Resize browser smaller to see hamburger menu

3. Make the changes below to show the menu by default.

   `src/app/mainnav/mainnav.component.html`

   ```diff
   <mat-sidenav-container class="sidenav-container">
     <mat-sidenav
       #drawer
       class="sidenav"
       fixedInViewport
       [attr.role]="(isHandset$ | async) ? 'dialog' : 'navigation'"
       [mode]="(isHandset$ | async) ? 'over' : 'side'"
   -    [opened]="(isHandset$ | async) === false"
     >

   ...
   <mat-sidenav-content>
       <mat-toolbar color="primary">
         <button
           type="button"
           aria-label="Toggle sidenav"
           mat-icon-button
           (click)="drawer.toggle()"
   -        *ngIf="isHandset$ | async"
         >
           <mat-icon aria-label="Side nav toggle icon">menu</mat-icon>
         </button>
         <span>my-mat-proj</span>
       </mat-toolbar>
   ```

<div style="page-break-after: always;"></div>

### Dashboard

1. Generate a dashboard component.

   ```
   ng generate @angular/material:dashboard dashboard
   ```

1. Add the component to the main content area.

   `src/app/mainnav/mainnav.component.html`

   ```diff
   ...
   -    <h1>Test</h1>
   +    <app-dashboard></app-dashboard>
     </mat-sidenav-content>
   </mat-sidenav-container>

   ```

### Table

1. Generate a table component.

   ```
   ng generate @angular/material:table my-table
   ```

1. Add the component to the main content area.

   `src/app/mainnav/mainnav.component.html`

   ```diff
   ...
       <app-dashboard></app-dashboard>
   +    <app-my-table></app-my-table>
     </mat-sidenav-content>
   </mat-sidenav-container>

   ```

<div style="page-break-after: always;"></div>

### Forms

1. Generate an address form component.

   ```
   ng generate @angular/material:address-form address-form
   ```

1. Add the component to the main content area.

   `src/app/mainnav/mainnav.component.html`

   ```diff
   ...
       <app-dashboard></app-dashboard>
       <app-my-table></app-my-table>
   +    <app-address-form></app-address-form>
     </mat-sidenav-content>
   </mat-sidenav-container>

   ```

#### Reference

- [Angular Material: Getting Started](https://material.angular.io/guide/getting-started)
- [Angular Material: Schematics](https://material.angular.io/guide/schematics)

<div style="page-break-after: always;"></div>

## Angular Material: CDK

Angular Material components use the `Component Development Kit` (CDK) library for reusable behavior and combines it with the styles to create components that implement [Google's Material Design Specification](https://material.io/design/).

### CDK: Installation

#### Steps

1. Install

```bash
npm install @angular/cdk@10 faker
```

> Note: `faker` is a JavaScript library used for generating data that we will use for one of the examples

2. Import the module

```ts
//app.module.ts
import {DragDropModule} from '@angular/cdk/drag-drop';
import { ScrollingModule } from '@angular/cdk/scrolling';

@NgModule({
  imports: [ ...,DragDropModule, ScrollingModule ]
})
export class AppModule { }
```

<div style="page-break-after: always;"></div>

### CDK: Drag & Drop

(using the `DragDropModule`)

The `@angular/cdk/drag-drop` module provides you with a way to easily and declaratively create drag-and-drop interfaces, with support for free dragging, sorting within a list, transferring items between lists, animations, touch devices, custom drag handles, previews, and placeholders, in addition to horizontal lists and locking along an axis.

#### Steps

1. Add the following styles

```css
/* 
src/styles.css 
*/

.example-container {
  width: 400px;
  max-width: 100%;
  margin: 0 25px 25px 0;
  display: inline-block;
  vertical-align: top;
}

.example-list {
  border: solid 1px #ccc;
  min-height: 60px;
  background: white;
  border-radius: 4px;
  overflow: hidden;
  display: block;
}

.example-boundary {
  width: 400px;
  height: 400px;
  max-width: 100%;
  border: dotted #ccc 2px;
}

.example-box {
  width: 200px;
  height: 200px;
  border: solid 1px #ccc;
  color: rgba(0, 0, 0, 0.87);
  cursor: move;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: #fff;
  border-radius: 4px;
  position: relative;
  z-index: 1;
  transition: box-shadow 200ms cubic-bezier(0, 0, 0.2, 1);
  box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14),
    0 1px 5px 0 rgba(0, 0, 0, 0.12);
}

.example-box:active {
  box-shadow: 0 5px 5px -3px rgba(0, 0, 0, 0.2), 0 8px 10px 1px rgba(0, 0, 0, 0.14),
    0 3px 14px 2px rgba(0, 0, 0, 0.12);
}

.example-box {
  padding: 20px 10px;
  border-bottom: solid 1px #ccc;
  color: rgba(0, 0, 0, 0.87);
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  box-sizing: border-box;
  cursor: move;
  background: white;
  font-size: 14px;
}

.cdk-drag-preview {
  box-sizing: border-box;
  border-radius: 4px;
  box-shadow: 0 5px 5px -3px rgba(0, 0, 0, 0.2), 0 8px 10px 1px rgba(0, 0, 0, 0.14),
    0 3px 14px 2px rgba(0, 0, 0, 0.12);
}

.cdk-drag-placeholder {
  opacity: 0;
}

.cdk-drag-animating {
  transition: transform 250ms cubic-bezier(0, 0, 0.2, 1);
}

.example-box:last-child {
  border: none;
}

.example-list.cdk-drop-list-dragging .example-box:not(.cdk-drag-placeholder) {
  transition: transform 250ms cubic-bezier(0, 0, 0.2, 1);
}
```

2. Create a `div` with the `cdKDrag` directive

```diff
// app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
+    <div class="example-box" cdkDrag>
+      Drag me around
+    </div>
  `,
  styles: []
})
export class AppComponent {}
```

3. In the browser you can now drag the div around the page.
4. You can also drag the div off the page.

5. Wrap the another `div` around the draggable `div`. This wrapper element will be the boundary within which you can drag.

```html
<div class="example-boundary">
  <div class="example-box" cdkDragBoundary=".example-boundary" cdkDrag>
    Drag me around
  </div>
</div>
```

> Be sure to include the `.` before the class name `example-boundary` in the `cdkDragBoundary` directive.

6. Drag the element and notice that it stays within the bounds of the boundary box.

> You can stop here but if time permits you can type the code below to create a list that reorders itself.

<div style="page-break-after: always;"></div>

#### Reorder List

1. Update the code

```ts
// app.component.ts

import { Component } from "@angular/core";
import { CdkDragDrop, moveItemInArray } from "@angular/cdk/drag-drop";

@Component({
  selector: "app-root",
  template: `
    <div cdkDropList class="example-list" (cdkDropListDropped)="drop($event)">
      <div class="example-box" *ngFor="let movie of movies" cdkDrag>
        {{ movie }}
      </div>
    </div>
  `,
  styles: [],
})
export class AppComponent {
  movies = [
    "Episode I - The Phantom Menace",
    "Episode II - Attack of the Clones",
    "Episode III - Revenge of the Sith",
    "Episode IV - A New Hope",
    "Episode V - The Empire Strikes Back",
    "Episode VI - Return of the Jedi",
    "Episode VII - The Force Awakens",
    "Episode VIII - The Last Jedi",
  ];

  drop(event: CdkDragDrop<string[]>) {
    moveItemInArray(this.movies, event.previousIndex, event.currentIndex);
  }
}
```

8. Comment out the first `example-box` style as shown below

```css
/* src/styles.css */

/* .example-box {
  width: 200px;
  height: 200px;
  border: solid 1px #ccc;
  color: rgba(0, 0, 0, 0.87);
  cursor: move;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: #fff;
  border-radius: 4px;
  position: relative;
  z-index: 1;
  transition: box-shadow 200ms cubic-bezier(0, 0, 0.2, 1);
  box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14),
    0 1px 5px 0 rgba(0, 0, 0, 0.12);
} */
```

9. You can now reorder the list by dragging and dropping the items.

> For additonal information see: [Drag & Drop Documentation](https://material.angular.io/cdk/drag-drop/overview)

<div style="page-break-after: always;"></div>

### CDK: Virtual Scrolling

(using the ScrollingModule)

The `<cdk-virtual-scroll-viewport>` displays large lists of elements performantly by only rendering the items that fit on-screen. Loading hundreds of elements can be slow in any browser; virtual scrolling enables a performant way to simulate all items being rendered by making the height of the container element the same as the height of total number of elements to be rendered, and then only rendering the items in view. Virtual scrolling is different from strategies like infinite scroll where it renders a set amount of elements and then when you hit the end renders the rest.

#### Steps

1. Add the following code:

```ts
//app.component.ts
import { Component } from "@angular/core";
import * as faker from "faker";

@Component({
  selector: "app-root",
  template: `
    <cdk-virtual-scroll-viewport itemSize="50" class="list">
      <div *cdkVirtualFor="let item of items" class="list-item">
        {{ item }}
      </div>
    </cdk-virtual-scroll-viewport>
  `,
  styles: [
    `
      .list {
        height: 200px;
        width: 200px;
        border: 1px solid black;
      }

      .list-item {
        height: 50px;
      }
    `,
  ],
})
export class AppComponent {
  items = Array.from({ length: 100000 }).map(() => `${faker.name.findName()}`);
}
```

> The key to the above example is that the `itemSize` property on the `<cdk-virtual-scroll-viewport>` must match the `.list-item` css class height.

4. View in the Chrome browser and open Chrome DevTools to the Elements tab
5. Scroll through the list and watch the items being generated as they come into view

> For additonal information see: [Scrolling Module Documentation](https://material.angular.io/cdk/scrolling/overview)

<div style="page-break-after: always;"></div>

#### Resources

- [Live drag/drop demo video](https://youtu.be/4EXQKP-Sihw?t=240)

- [Article on Angular Material Setup](https://material.angular.io/guide/schematics)

- [Slides: The CDK is the Coolest Thing You are not Using](g.co/ng/conf19-components-slides)

- [Infinite Virtual Scroll using Angular CDK](https://angularfirebase.com/lessons/infinite-virtual-scroll-angular-cdk/)

<div style="page-break-after: always;"></div>

### Bootstrapping an Application

```ts
import "./polyfills";

// app/app.component.ts
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: "<h1>Hello Angular</h1>",
})
export class AppComponent {}

import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";

// app/app.module.ts
@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule],
  bootstrap: [AppComponent],
})
export class AppModule {}

// app/main.ts
import { platformBrowserDynamic } from "@angular/platform-browser-dynamic";
platformBrowserDynamic().bootstrapModule(AppModule);
```

<div style="page-break-after: always;"></div>

## Lifecycle Hooks

A component has a lifecycle managed by Angular.

Angular **creates** and renders components along with their children, checks when their data-bound _properties_ **change**, and **destroys** them before removing them from the DOM.

Angular offers **lifecycle hooks** that provide visibility into these key life moments and the ability to act when they occur.

### Starting Point

Open `demos\start\` directory.

```
git checkout input-property -f
git clean -df
```

### Init & Changes

**`src\app\app.component.ts`**

```ts
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `
    <app-fruit-list [fruits]="data"></app-fruit-list>
    <button (click)="onClickChange()">Change List</button>
  `,
  styles: [],
})
export class AppComponent {
  data: string[] = ["Apple", "Orange", "Plum"];
  onClickChange() {
    this.data = ["Banana", "Kiwi", "Grape"];
  }
}
```

**`src\app\fruit-list\fruit-list.component.ts`**

```ts
import {
  Component,
  OnInit,
  Input,
  OnChanges,
  SimpleChanges,
} from "@angular/core";

@Component({
  selector: "app-fruit-list",
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">
        {{ fruit }}
      </li>
    </ul>
  `,
  styles: [],
})
export class FruitListComponent implements OnInit, OnChanges {
  @Input()
  fruits: string[];
  constructor() {
    console.log("Constructor");
  }
  ngOnChanges(changes: SimpleChanges): void {
    console.log("OnChanges");
    console.log("Previous Values: " + changes.fruits.previousValue);
    console.log("Current Values: " + changes.fruits.currentValue);
  }

  ngOnInit() {
    console.log("OnInit");
  }
}
```

**Results**

Refresh Page:

```
Constructor
OnChanges
Previous Values: undefined
Current Values: ["Apple", "Orange", "Plum"]
OnInit
```

Click Change List:

```
OnChanges
Previous Values: ["Apple", "Orange", "Plum"]
Current Values: ["Banana", "Kiwi", "Grape"]
```

### Destroy

**`src\app\app.component.ts`**

```diff
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <app-fruit-list [fruits]="data"
+   *ngIf="showList"></app-fruit-list>
    <button (click)="onClickChange()">Change List</button>
+    <br />
+    <button (click)="onClickRemove()">Remove</button>
  `,
  styles: []
})
export class AppComponent {
  data: string[] = ['Apple', 'Orange', 'Plum'];
  showList = true;
  onClickChange() {
    this.data = ['Banana', 'Kiwi', 'Grape'];
  }
+  onClickRemove() {
+    this.showList = !this.showList;
+  }
}
```

**`src\app\fruit-list\fruit-list.component.ts`**

```diff
import {
  Component,
  OnInit,
  Input,
  OnChanges,
  SimpleChanges,
+  OnDestroy
} from '@angular/core';

@Component({
  selector: 'app-fruit-list',
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">
        {{ fruit }}
      </li>
    </ul>
  `,
  styles: []
})
export class FruitListComponent implements OnInit, OnChanges,
+ OnDestroy {
  @Input()
  fruits: string[];
  constructor() {
    console.log('Constructor');
  }
  ngOnChanges(changes: SimpleChanges): void {
    console.log('OnChanges');
    console.log('Previous Values: ' + changes.fruits.previousValue);
    console.log('Current Values: ' + changes.fruits.currentValue);
  }
  ngOnInit() {
    console.log('OnInit');
  }
+  ngOnDestroy(): void {
+    console.log('Destroyed');
+  }
}
```

**Results**

Click Remove

```
Destroyed
```

### Final Code

**`src\app\app.component.ts`**

```ts
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `
    <app-fruit-list [fruits]="data" *ngIf="showList"></app-fruit-list>
    <button (click)="onClickChange()">Change List</button>
    <br />
    <button (click)="onClickRemove()">Remove</button>
  `,
  styles: [],
})
export class AppComponent {
  data: string[] = ["Apple", "Orange", "Plum"];
  showList = true;
  onClickChange() {
    this.data = ["Banana", "Kiwi", "Grape"];
  }
  onClickRemove() {
    this.showList = !this.showList;
  }
}
```

**`src\app\fruit-list\fruit-list.component.ts`**

```ts
import {
  Component,
  OnInit,
  Input,
  OnChanges,
  SimpleChanges,
  OnDestroy,
} from "@angular/core";

@Component({
  selector: "app-fruit-list",
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">
        {{ fruit }}
      </li>
    </ul>
  `,
  styles: [],
})
export class FruitListComponent implements OnInit, OnChanges, OnDestroy {
  @Input()
  fruits: string[];
  constructor() {
    console.log("Constructor");
  }
  ngOnChanges(changes: SimpleChanges): void {
    console.log("OnChanges");
    console.log("Previous Values: " + changes.fruits.previousValue);
    console.log("Current Values: " + changes.fruits.currentValue);
  }
  ngOnInit() {
    console.log("OnInit");
  }
  ngOnDestroy(): void {
    console.log("Destroyed");
  }
}
```

### ViewChild(ren) & AfterViewInit

```
ng g c hello-world
```

**`src\app\app.component.ts`**

```ts
import { Component, ViewChild, OnInit, AfterViewInit } from "@angular/core";
import { FruitListComponent } from "./fruit-list/fruit-list.component";
import { HelloWorldComponent } from "./hello-world/hello-world.component";

@Component({
  selector: "app-root",
  template: `
    <app-hello-world></app-hello-world>
    <app-fruit-list [fruits]="data" *ngIf="showList"></app-fruit-list>
    <button (click)="onClickChange()">Change List</button>
    <br />
    <button (click)="onClickRemove()">Remove</button>
  `,
  styles: [],
})
export class AppComponent implements OnInit, AfterViewInit {
  @ViewChild(HelloWorldComponent, { static: true }) helloWorldComponent;
  @ViewChild(FruitListComponent, { static: false }) fruitListComponent;
  data: string[] = ["Apple", "Orange", "Plum"];
  showList = true;

  ngOnInit(): void {
    console.log("App OnInit: ");
    console.log("ViewChild (hello):", this.helloWorldComponent);
    console.log("ViewChild: (fruit list)", this.fruitListComponent);
  }

  ngAfterViewInit(): void {
    console.log("App AfterViewInit: ");
    console.log("ViewChild (hello):", this.helloWorldComponent);
    console.log("ViewChild: (fruit list)", this.fruitListComponent);
  }

  onClickChange() {
    this.data = ["Banana", "Kiwi", "Grape"];
  }
  onClickRemove() {
    this.showList = !this.showList;
  }
}
```

**`src\app\fruit-list\fruit-list.component.ts`**

```ts
import {
  Component,
  OnInit,
  Input,
  OnChanges,
  SimpleChanges,
  OnDestroy,
} from "@angular/core";

@Component({
  selector: "app-fruit-list",
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">
        {{ fruit }}
      </li>
    </ul>
  `,
  styles: [],
})
export class FruitListComponent implements OnInit, OnChanges, OnDestroy {
  @Input()
  fruits: string[];
  constructor() {
    console.log("Constructor");
  }
  ngOnChanges(changes: SimpleChanges): void {
    console.log("FruitList OnChanges");
    console.log("Previous Values: " + changes.fruits.previousValue);
    console.log("Current Values: " + changes.fruits.currentValue);
  }
  ngOnInit() {
    console.log("FruitList OnInit");
  }
  ngOnDestroy(): void {
    console.log("FruitList Destroyed");
  }
}
```

---

### ContentChild(ren) & AfterContentInit

- ViewChildren don’t include elements that exist within the ng-content tag.
- ContentChildren includes only elements that exists within the ng-content tag.

**`src\hello-world\hello-world.component.ts`**

```ts
import {
  Component,
  OnInit,
  ContentChild,
  AfterViewInit,
  AfterContentInit,
} from "@angular/core";

@Component({
  selector: "app-hello-world",
  template: ` <p>Hello World! My name is: <ng-content></ng-content></p> `,
  styles: [],
})
export class HelloWorldComponent
  implements OnInit, AfterViewInit, AfterContentInit
{
  @ContentChild("nameContent", { static: true }) nameContent;
  constructor() {}

  ngOnInit() {
    console.log(
      "OnInit: nameContent available only if static is true. ",
      this.nameContent
    );
  }
  ngAfterContentInit() {
    console.log("AfterContentInit: nameContent available. ", this.nameContent);
  }
  ngAfterViewInit() {
    console.log("AfterViewInit: nameContent available. ", this.nameContent);
  }
}
```

**`src\app\fruit-list\fruit-list.component.ts`**

```ts
import {
  Component,
  OnInit,
  Input,
  OnChanges,
  SimpleChanges,
  OnDestroy,
} from "@angular/core";

@Component({
  selector: "app-fruit-list",
  template: `
    <ul>
      <li *ngFor="let fruit of fruits">
        {{ fruit }}
      </li>
    </ul>
  `,
  styles: [],
})
export class FruitListComponent implements OnInit, OnChanges, OnDestroy {
  @Input()
  fruits: string[];
  constructor() {
    console.log("Constructor");
  }
  ngOnChanges(changes: SimpleChanges): void {
    console.log("FruitList OnChanges");
    console.log("Previous Values: " + changes.fruits.previousValue);
    console.log("Current Values: " + changes.fruits.currentValue);
  }
  ngOnInit() {
    console.log("FruitList OnInit");
  }
  ngOnDestroy(): void {
    console.log("FruitList Destroyed");
  }
}
```

**`src\app\app.component.ts`**

```ts
import { Component, ViewChild, OnInit, AfterViewInit } from "@angular/core";
import { FruitListComponent } from "./fruit-list/fruit-list.component";
import { HelloWorldComponent } from "./hello-world/hello-world.component";

@Component({
  selector: "app-root",
  template: `
    <app-hello-world>
      <h2 #nameContent>Bond, James Bond</h2>
    </app-hello-world>
  `,
  styles: [],
})
export class AppComponent implements OnInit, AfterViewInit {
  @ViewChild(HelloWorldComponent, { static: true }) helloWorldComponent;

  ngOnInit(): void {
    console.log("App OnInit: ");
    console.log("ViewChild (hello):", this.helloWorldComponent);
  }

  ngAfterViewInit(): void {
    console.log("App AfterViewInit: ");
    console.log("ViewChild (hello):", this.helloWorldComponent);
  }
}
```

### Reference

- [Lifecycle Hooks Documentation](https://angular.io/guide/lifecycle-hooks)
- [Understanding View Children and ContentChildren](https://netbasal.com/understanding-viewchildren-contentchildren-and-querylist-in-angular-896b0c689f6e)

<div style="page-break-after: always;"></div>

## Libraries

### Your First Library

1. Run the commands:

   ```
   ng new my-workspace --createApplication="false"
   cd my-workspace
   ng generate application my-first-app
   ng generate library my-lib
   ng build my-lib
   ```

1. Import `MyLibModule` in the app.

   **`my-first-app\src\app\app.module.ts`**

   ```diff
   import { BrowserModule } from '@angular/platform-browser';
   import { NgModule } from '@angular/core';

   import { AppComponent } from './app.component';
   + import { MyLibModule } from 'my-lib';

   @NgModule({
     declarations: [AppComponent],
     imports: [BrowserModule
   +  ,MyLibModule
     ],
     providers: [],
     bootstrap: [AppComponent]
   })
   export class AppModule {}
   ```

1. Delete the html in the AppComponent template and add the component from `my-lib`.

   **`my-first-app\src\app\app.component.html`**

   ```html
   <lib-my-lib></lib-my-lib>
   ```

1. Change the lib component.
1. Notice the app doesn't update.
1. Rebuild and the app updates.

   ```
   ng build my-lib
   ```

   > No need to stop and start `ng serve`

   OR

   ```
   ng build my-lib --watch
   ```

   > Library triggers rebuild automatically when changed.

### Issues

If you receive this error after running the command `ng build my-lib`:

```
BrowserslistError: Unknown version 67 of android
```

- Delete `node_modules` and `package-lock.json`
- Ensure these versions:
  ```json
    "devDependencies": {
    "@angular-devkit/build-angular": "^0.801.3",
    "@angular-devkit/build-ng-packagr": "^0.801.3",
    ...
  ```
- Run `npm install` again.
- [See this github issue for more information](https://github.com/ng-packagr/ng-packagr/issues/1411)

### Reference

- [File Structure: Library Project Files](https://angular.io/guide/file-structure#library-project-files)
- [Creating Libraries Official Documentation](https://angular.io/guide/creating-libraries)
- [Using npm Link](https://medium.com/dailyjs/how-to-use-npm-link-7375b6219557)
- [Creating Your Own Libraries with the Angular CLI](https://blog.angulartraining.com/create-your-own-libraries-with-angular-cli-7b434600bbb7)

<div style="page-break-after: always;"></div>

<div style="page-break-after: always;"></div>

## Setup

### Creating this project

Not done in class just checkout start branch.

```
ng new demos --routing --inline-style --inline-template --skip-tests --skip-install --strict false
```

> Notice the flags --inline-style --inline-template so separate html and css files are not generated for each component.

1. Open `package.json` and remove `devDependencies` related to testing.
2. Delete e2e folder.
3. npm install

<div style="page-break-after: always;"></div>

### Creating the http-start branch

Not done in class just checkout http-start branch.

```shell
git checkout start
npm install json-server
mkdir api
```

Copy db.json from here: https://jsonplaceholder.typicode.com/db
into the api folder.

Add script to `package.json`

```diff
"scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e",
+   "api": "json-server ./api/db.json"
  },
```

<div style="page-break-after: always;"></div>

## Feedback

I appreciate all feedback. All pdf manuals are protected but are able to be annotated. Send feedback to craig at funnyant dot com.
