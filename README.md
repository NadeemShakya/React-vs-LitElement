# :pencil: React-vs-LitElement

A detailed comparison between two of the finest front-end libraries for building re-usable web components.

## 1. Let's see what their documentation speaks for themselves :loudspeaker:

<table border="0">
<tr>
  <th>React</th>
  <th>LitElement</th>
</tr>
 <tr>
   <td> 
     <h6>Declarative</h6>
      React makes it painless to create interactive UIs. Design simple views for each state in your application,         and React will efficiently update and render just the right components when your data changes.
      Declarative views make your code more predictable and easier to debug.
   </td>
   <td> 
      <h6>Delightfully declarative</h6>
      LitElement’s simple, familiar development model makes it easier than ever to build Web Components.
      Express your UI declaratively, as a function of state. No need to learn a custom templating language – you can use the full power of JavaScript in your templates. Elements update automatically when their properties change.
   </td>
 </tr>
 
  <tr>
   <td> 
      <h6>Component Based</h6>
     Build encapsulated components that manage their own state, then compose them to make complex UIs.
     Since component logic is written in JavaScript instead of templates, you can easily pass rich data through        your app and keep state out of the DOM
  </td>
   <td> 
         <h6>Fast and light</h6>
      Whether your end users are in emerging markets or Silicon Valley, they’ll appreciate that LitElement is extremely fast.
      <br/>
      LitElement uses lit-html to define and render HTML templates. DOM updates are lightning-fast, because lit-html only re-       renders the dynamic parts of your UI – no diffing required.
    </td>
 </tr>
 
 <tr>
   <td>
    <h6>Learn Once, Write Anywhere</h6> 
      We don’t make assumptions about the rest of your technology stack, so you can develop new features in React       without rewriting existing code.
      React can also render on the server using Node and power mobile apps using React Native.
    </td>
   <td> 
    <h6>Seamlessly interoperable</h6> 
     LitElement follows the Web Components standards, so your components will work with any framework.
     LitElement uses Custom Elements for easy inclusion in web pages, and Shadow DOM for encapsulation. There’s no new abstraction on top of the web platform.
  </td>
 </tr>
</table>

## 2. DOM Manipulation :computer:

### React

React uses the concept of Virtual DOM for the DOM manipulation. Virtual DOM is an in-memory allocation of the DOM nodes. The representation of a UI is kept in memory and synced with the “real” DOM by a library such as ReactDOM. This process is called reconciliation.

<b>How is Virtual DOM efficient?</b>

Virtual DOM avoids the unnecessary changes to the DOM, which are perfomance expensive. Incase of a single change, rather than updating the whole DOM, Virtual DOM creates a new state of the updated Virtual DOM and compares it with the non-updated Virtual DOM. It finds out the nodes that need to be changed by comparing the non-updated and updated Virtual DOM and then only updates those particular nodes in the real DOM. The process of comparing the non-updated and updated Virtual DOM to find out the changes is called <b>Diffing</b>.

[Virtual DOM and Internals](https://reactjs.org/docs/faq-internals.html)
[DOM Manipulation in React](https://dzone.com/articles/dom-manipulation-in-react)

### LitElement

LitElement uses the concept of Shadow DOM for the DOM Manipulation. Shadow DOM provides encapsulation of the web components in terms of the styling and properties.

A single custom element can implement more-or-less complex logic combined with more-or-less complex DOM. Shadow DOM refers to the ability of the browser to include a subtree of DOM elements into the rendering of a document, but not into the main document DOM tree.

<b>How is Shadow DOM efficient?</b>

Shadow DOM provides local scoping for HTML and CSS. Shadow DOM's encapsulation helps to reduce any unnecessary DOM re-renders due to naming conflicts. Also, rather than re-rendering the whole DOM, the concept of separated componets causes only the sub-tree of the real DOM to be updated depending on the changes made.

<b>Lit Element uses Lit-html</b>

lit-html, a HTML templating library lets you write HTML templates in JavaScript, then efficiently render and re-render those templates together with data to create and update DOM. Lit-html uses the concept of tagged template literals, in which it separates out the static and dynamic contents of the string literals and focuses to only update the changed nodes from the dynamic contents.

[Virtual DOM vs Shadow DOM](https://vuejsfeed.com/blog/learn-the-differences-between-shadow-dom-and-virtual-dom)
[Understanding Shadow DOM](https://blog.logrocket.com/understanding-shadow-dom-v1-fa9b81ebe3ac/)

#### Virtual DOM vs lit-html

In Virtual DOM, the number of comparisions(between updated and non-updated Virtual DOM) increases with the increase of nodes, whether it is a static node or a dynamic node. So, the number of comparisions are proportional to the number of nodes rather than the number of changes.

But, In lit-html, as we separate out the static and dynamic content from the overall content, lit-html can directly focus on making comparisions on the dynamic contents to find out the changes. This leads to having the static content untouched which reduces the total number of comparisions to be made.

[Surma & Jake Archibald talk Virtual DOM vs lit-html ](https://www.youtube.com/watch?v=uCHZJy2n8Qs)
