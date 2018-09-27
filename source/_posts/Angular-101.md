---
title: Angular 101
date: 2018-09-27 11:42:02
tags: Angular
---
# Modules
## NgModules
Angular apps are modular and Angular has its own modularity system called NgModules. **NgModules are containers** for a cohesive block of code dedicated to an application domain, a workflow, or a closely related set of capabilities. **They can contain components, service providers, and other code files whose scope is defined by the containing NgModule**. They can import functionality that is exported from other NgModules, and export selected functionality for use by other NgModules.

Every Angular app has **at least one NgModule class**, the root module, which is conventionally named AppModule and resides in a file named app.module.ts. You launch your app by bootstrapping the root NgModule.

While a small application might have only one NgModule, most apps have many more feature modules. The root NgModule for an app is so named because it can include child NgModules in a hierarchy of any depth.

## NgModules and JavaScript modules
The NgModule system is different from and unrelated to the JavaScript (ES2015) module system for managing collections of JavaScript objects. These are complementary module systems that you can use together to write your apps.

In JavaScript **each file is a module** and all objects defined in the file belong to that module. The module declares some objects to be public by marking them with the export key word. Other JavaScript modules use import statements to access public objects from other modules.

# Components
**Every component must be declared in exactly one NgModule.**
## MVC/MVVM
model-view-controller (MVC) or model-view-viewmodel (MVVM).
In Angular, the component plays the part of the controller/viewmodel, and the template represents the view.
## Binding
<img src="https://angular.io/generated/images/guide/architecture/databinding.png">
### One way binding
```
<li>{{hero.name}}</li>
<app-hero-detail [hero]="selectedHero"></app-hero-detail>
<li (click)="selectHero(hero)"></li>
```
* The &#123;&#123;hero.name&#125;&#125; interpolation displays the component's `hero.name` property value within the `<li>` element.
* The `[hero]` property binding passes the value of selectedHero from the parent HeroListComponent to the hero property of the child HeroDetailComponent.
* The `(click)` event binding calls the component's selectHero method when the user clicks a hero's name.

### Two way binding
**[(ngModel)]** is Angular's two-way data binding syntax. Remember to import FormsModule in AppModule when using ngModel.
```
<input [(ngModel)]="hero.name">
```
## Event
### Event Binding
A name between parentheses — for example, `(click)` — identifies the target event. In the following example, the target is the button's click event.
```
<button (click)="onSave()">Save</button>
```
### Event handler
Add `onSave()` method for the above event.

## Style
Styles and stylesheets identified in `@Component` metadata are **scoped** to that specific component.
## Pipes
Pipes are a good way to format strings, currency amounts, dates and other display data. Angular ships with several built-in pipes and you can create your own.

## Directives
A component is technically a directive.
### Structural directives
```
<li *ngFor="let hero of heroes"></li>
<app-hero-detail *ngIf="selectedHero"></app-hero-detail>
```
`*ngFor` is an iterative; it tells Angular to stamp out one `<li>` per hero in the heroes list.
`*ngIf` is a conditional; it includes the HeroDetail component only if a selected hero exists.
### Attribute directives
```
<input [(ngModel)]="hero.name">
```
* ngModel
* ngSwitch
* ngStyle and ngClass

# Services and DI
DI is wired into the Angular framework and used everywhere to provide new components with the services or other things they need. Components consume services; that is, **you can inject a service into a component, giving the component access to that service class**.

