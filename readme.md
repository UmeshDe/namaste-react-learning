# Assignment 01 - Inception

**1. What is Emmet ?**
Emmet is a toolkit that helps web developers to write HTML and CSS code faster and more efficiently.  
It allows you to create large chunks of code with just a few keystrokes by using a shorthand syntax. Initially known as "Zen Coding," Emmet can expand abbreviations into full-fledged HTML or CSS structures.

**2. Difference between a Library and Framework ?**
React is a library, not a framework, because it focuses solely on the UI layer and can be integrated into specific parts of a webpage rather than controlling the entire application. Unlike frameworks that enforce a particular structure, React allows for flexible, partial use within an existing project. This makes it more modular and unopinionated compared to full-fledged frameworks like Angular.

**3. What is CDN ? Why do we use it ?**
A Content Delivery Network (CDN) is a system of distributed servers that deliver web content to users based on their geographic location. It reduces latency by caching content like images, videos, and scripts on servers closer to the user, improving load times and performance.

We use CDNs to:

*Enhance Speed: Deliver content faster by minimizing the distance data travels.
Reduce Server Load: Offload traffic from the origin server to multiple distributed servers.
Improve Availability: Ensure content remains accessible even during traffic spikes or server outages.*

**4. Why is React known as React ?**
React is called "React" because of its ability to efficiently "react" to changes in data and update the user interface accordingly. It achieves this through its reactive nature, meaning that when the underlying data changes, React automatically re-renders only the components that need updating.

React's Virtual DOM plays a key role in this reactivity. It compares the current state of the UI with the previous state and updates only the necessary parts, ensuring fast and efficient rendering. This reactive approach is what gives React its name.

**5. What is crossorigin in script tag ?**
The crossorigin attribute in the script tag is used to manage how browsers handle cross-origin requests for external resources like JavaScript files. When loading a script from a different domain, the crossorigin attribute helps control how browsers treat security and resource-sharing policies, especially when dealing with CORS (Cross-Origin Resource Sharing).

There are two common values for crossorigin:

i. anonymous:

Sends the request without credentials (cookies, HTTP authentication).
Use this when you don't need to send user-specific data with the request.

```html
<script src="https://example.com/script.js" crossorigin="anonymous"></script>
```

ii. use-credentials:

Sends the request with credentials (cookies, HTTP authentication).
Use this when you need to send user-specific data.

```html
<script src="https://example.com/script.js" crossorigin="use-credentials"></script>
```

**6. What is diference between React and ReactDOM ?**
###### React
React is the core library used for building user interfaces. It provides the functionality to create components, manage their state, and handle the logic for rendering the UI.

###### ReactDOM
It provides methods to interact with the DOM (Document Object Model), enabling React to render components to the actual browser.

**7. What is the difference between react.development.js and react.production.js files via CDN ?**
###### react.development.js
This version is meant for development and debugging.
Contains helpful error messages, warnings, and detailed logs in the console to assist with troubleshooting during development.
Provides more informative error reporting and checks, making it easier to catch mistakes or potential issues.

###### react.production.js
This version is optimized for production use.
Strips out all development-related code, like warnings and detailed error messages, to reduce file size.
Minified to improve loading times and reduce the application's footprint.

**8. What is async and defer ?**
async and defer are attributes used in the script tag to control how scripts are loaded and executed in a web page, particularly in relation to the parsing of the HTML document. Both attributes improve page performance and enhance the user experience by preventing blocking of the HTML rendering.

1. async:
Loading: When a script is marked with async, it is fetched asynchronously while the HTML document continues to be parsed. This means the browser can load the script file at the same time it is parsing the page.
Execution: Once the script is downloaded, it executes immediately, regardless of whether the HTML parsing is complete. This can potentially interrupt the rendering of the page if the script takes time to execute.
Use Case: Best used for scripts that are independent and don’t rely on other scripts or DOM elements being fully parsed.
```html
<script src="script.js" async></script>
```

2. defer:
Loading: Like async, when a script is marked with defer, it is fetched asynchronously while the HTML document is still being parsed.
Execution: However, scripts with defer are executed in the order they appear in the document and only after the HTML parsing is complete. This ensures that all DOM elements are available when the script runs, making it safe for scripts that manipulate the DOM.
Use Case: Ideal for scripts that depend on the DOM being fully loaded or if they rely on other scripts being executed in a specific order.
```html
<script src="script.js" defer></script>
```

**8. Arrow functions ?**
Arrow functions are a concise way to write function expressions in JavaScript, introduced in ES6 (ECMAScript 2015). They offer several benefits over traditional function expressions, including a shorter syntax and the preservation of the lexical this context. 

```javascript
const functionName = (parameters) => {
  // function body
};
```

Key Features:

1. Concise Syntax:
If there is only one parameter, parentheses can be omitted:
```javascript
const square = x => x * x;
```
If the function body contains a single expression, the curly braces and return statement can also be omitted:
```javascript
const add = (a, b) => a + b;
```
2. Lexical this Binding:
Arrow functions do not have their own this context. Instead, they inherit this from the surrounding lexical scope (the context in which they were defined). This is particularly useful when using methods that need to maintain the context of this inside callbacks.
```javascript
function Timer() {
  this.seconds = 0;

  setInterval(() => {
    this.seconds++; // `this` refers to the Timer instance
    console.log(this.seconds);
  }, 1000);
}

const timer = new Timer();
```
3. Cannot be Used as Constructors:
Arrow functions cannot be used with the new keyword. They do not have a prototype property, which means they cannot create instances.

4. No arguments Object:
Arrow functions do not have their own arguments object. If you need access to arguments, you would have to use a regular function or rest parameters.

```javascript
const sum = (...args) => args.reduce((a, b) => a + b, 0);
```