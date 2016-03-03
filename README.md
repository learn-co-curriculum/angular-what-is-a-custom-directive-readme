# What is a custom Directive?

## Overview

One of the massive powerful aspects of Angular is the ability to actually be able to create our own directives.

## Objectives

- Describe what components are
- Describe custom Directives
- Create a custom Directive

## Components

Nowadays, most frontend applications are made up of small, reusable components. If we imagine a car, it would be made up with components such as wheels, windows, engine, etc.

We can create these components using directives. We've already used directives that Angular gives us, but we can also make our own.

Directives can both be HTML attributes and HTML elements. Most of our directives will be HTML elements, as they will have their own template inside of themselves instead of modifying the behaviour of existing elements.

If we imagine an `ng-repeat`, that modifies the behaviour of the element it is placed on by repeating it for every item in an array.

However, we might create a custom directive called "dropdown". This dropdown directive will have it's own template that will get put into the DOM, so we create it as a HTML element instead.

## Creating a custom directive

Much like services and controllers, we can use the `.directive` function to create our directives.

Our directive names are what we then use to reference them in the DOM. However, as the DOM is case-insensitive, we change the captial letters in our name to hypens. For instance, the directive name `myDirective` becomes `<my-directive></my-directive>`.

Let's look at a custom directive:

```js
function MyDirective() {
	return {
		template: '<div>Hello world!</div>'
	};
}

angular
	.module('app')
	.directive('myDirective', MyDirective);
```

You'll notice that in our directive function we return an object - this describes all the functionality and configuration of our directive.

We can then use `myDirective` in the DOM, and it will be replaced by the template you see above.

```
<my-directive></my-directive>
```

Would then be transformed into

```
<my-directive>
	<div>
		Hello world!
	</div>
</my-directive>
```

When rendered by Angular! This is an extremely basic directive, we're going to look into making them much more advanced in the next few readmes!