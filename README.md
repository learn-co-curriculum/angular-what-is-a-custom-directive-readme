# What is a custom Directive?

## Overview

One of the massive powerful aspects of Angular is the ability to actually be able to create our own directives.

## Objectives

- Describe what components are
- Describe custom Directives
- Create a custom Directive

## Components

Nowadays, most frontend applications are made up of small, reusable components. If we imagine a car, it would be made up with components such as wheels, windows, engine, etc. In our case, the components that make up our website would be a header, footer, dropdown menu, toggles, etc.

We can create these components using directives. We've already used directives that Angular gives us, but we can also make our own.

Directives can both be HTML attributes and HTML elements. Most of our directives will be HTML elements, as they will have their own template inside of themselves instead of modifying the behaviour of existing elements.

We might create a custom directive called "dropdown". This dropdown directive will have it's own template that will get put into the DOM, so we create it as a HTML element instead.

In plain JavaScript, our dropdown might look [something like this](https://jsfiddle.net/ogyzmx7r). There's a lot of code here that will be common to other elements, such as selecting and replacing elements from the page. Now let's check out [what it is like in Angular](https://jsfiddle.net/ogyzmx7r/1/). You'll notice how we use a custom HTML element (`<dropdown>`) and the code we need is a lot simpler and easier to read! Let's learn all about them.

## Creating a custom directive

Much like services and controllers, we can use the `.directive` function to create our directives.

Our directive names are what we then use to reference them in the DOM. However, as the DOM is case-insensitive, we change the capital letters in our name to hypens. For instance, the directive name `myDirective` becomes `<my-directive></my-directive>`. `userDropdownList` will become `<user-dropdown-list></user-dropdown-list>`.

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

You'll notice that in our directive function we return an object - this describes all the functionality and configuration of our directive. The function name is a capital letter but the directive name is always camel case - this is to keep function names consistent when compared to our custom services, filters, etc.

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

<p class='util--hide'>View <a href='https://learn.co/lessons/angular-what-is-a-custom-directive-readme'>What Is A Custom Directive?</a> on Learn.co and start learning to code for free.</p>
