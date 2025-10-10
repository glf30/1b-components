# Components

All the pieces of your web app can be thought of as components. For example, let's say you have a web app that allows users to search for different types of wine based on what they like and the app will display matching wine with reviews and links to purchase. The search box can be one component called Search, the area that displays the search results can be another component called Results. Each individual search result can be a component called Wine. Inside each Wine component can be broken down into child components for each part such as Description, Reviews, and Purchase buttons. Essentially, components are the individual building blocks of our user interface. React makes it easy to create reusable components can can be copied from project to project. React also ensures that changes to our application state will be displayed in our components. For example, when a user clicks the Purchase button component the Cart component should update to show the products in cart count has increased to 1 item in their Cart.

## Functional Components

React supports functional components that behave similarly but are written a bit different. Let's see what our class component would look like as a functional component.

```jsx
import React from "react";

const Food = () => {
  return <h2>Pizza</h2>;
}

export default Food;
```

All of these ways of writing functional components will produce the same result. Now you know how to recognize them in code whatever form they may take.

## Nesting Components

We can nest one component inside another by including it by name inside a block of JSX code. We refer to them just as if they're built-in HTML elements, usually as self-closing tags.

```jsx
import React from "react";

function Task () {
  return <li>Walk the dog</li>;
}

function TaskList () {
  return (
    <ul>
      <Task />
    </ul>
  );
}
```

As you can see we nested the Task component inside of the TaskList component. If we tell ReactDOM to render the TaskList component, this is what we would see in the browser.

```html
<ul>
  <li>Walk the dog</li>
</ul>
```

This also works the same for functional components

```jsx
import React from 'react';

function Task() {
  return <li>Walk the dog</li>;
}

function TaskList {
  return <ul>
           <Task />
         </ul>;
}
```

Nesting components allows us to separate logic, and to break otherwise complicated components down into smaller more manageable parts and pieces.

Also, don't forget if the components you are nesting are in separate files, use `export` and `import` to make them available in other files.
