<link href="main.css" rel="stylesheet"></link>

# :pencil: React-vs-LitElement
A detailed comparison between two of the finest front-end libraries for building re-usable web components.

## Let's see what their documentation speaks for themselves


<table border="0">
 <tr style="text-align: center">
   <td> 
     <b class="cell-header">Declarative</b> <br /><br />
        React makes it painless to create interactive UIs. Design simple views for each state in your application,         and React will efficiently update and render just the right components when your data changes.
        Declarative views make your code more predictable and easier to debug.
   </td>
   <td> 
     <b>Delightfully declarative</b> <br />
      LitElement’s simple, familiar development model makes it easier than ever to build Web Components.
Express your UI declaratively, as a function of state. No need to learn a custom templating language – you can use the full power of JavaScript in your templates. Elements update automatically when their properties change.
   </td>
 </tr>
 
 <tr>
   <td> 
     <b>Component-Based</b><br /> 
     Build encapsulated components that manage their own state, then compose them to make complex UIs.
     Since component logic is written in JavaScript instead of templates, you can easily pass rich data through        your app and keep state out of the DOM
  </td>
   <td> 
     <b>Fast and Light</b><br />
      Whether your end users are in emerging markets or Silicon Valley, they’ll appreciate that LitElement is extremely fast.
      LitElement uses lit-html to define and render HTML templates. DOM updates are lightning-fast, because lit-html only re-       renders the dynamic parts of your UI – no diffing required.
    </td>
 </tr>
 
 <tr>
   <td> 
     <b>Learn Once, Write Anywhere</b><br />
      We don’t make assumptions about the rest of your technology stack, so you can develop new features in React       without rewriting existing code.
      React can also render on the server using Node and power mobile apps using React Native.
    </td>
   <td> 
     <b>Seamlessly interoperable</b> <br />
     LitElement follows the Web Components standards, so your components will work with any framework.
     LitElement uses Custom Elements for easy inclusion in web pages, and Shadow DOM for encapsulation. There’s no new abstraction on top of the web platform.
  </td>
 </tr>
</table>
