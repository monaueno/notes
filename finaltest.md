## CS 260 Final Exam Questions

### 1. What is the default port for HTTP/HTTPS/SSH? 
HTTP: 80, HTTPS: 443, SSH: 22

### 2. What does an HTTP status code in the range of 300/400/500 indicate?
Errors 300: Redirection, 400: client errors, 500: server errors

### 3. What does the HTTP header content-type allow you to do?
The Content-Type HTTP header (also known as media type or MIME type) is a representation header used to inform servers/browsers about the original media type of an asset before any encoding takes place[1]. The content type header contains two values – media type and subtype.

### 4. What does a “Secure cookie”/”Http-only cookie”/”Same-site cookie” do? https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies
Secure Cookie: only sent to the server with an encrypted request over the HTTPS protocol. It's never sent with unsecured HTTP (except on localhost), which means man-in-the-middle attackers can't access it easily. Insecure sites (with http: in the URL) can't set cookies with the Secure attribute. However, don't assume that Secure prevents all access to sensitive information in cookies. For example, someone with access to the client's hard disk (or JavaScript if the HttpOnly attribute isn't set) can read and modify the information. A cookie with the Secure attribute is only sent to the server with an encrypted request over the HTTPS protocol

Http-only Cookie: can't be accessed by JavaScript, for example using Document.cookie; it can only be accessed when it reaches the server. Cookies that persist user sessions for example should have the HttpOnly attribute set — it would be really insecure to make them available to JavaScript. This precaution helps mitigate cross-site scripting (XSS) attacks.

Same-site cookie: lets servers specify whether/when cookies are sent with cross-site requests — i.e. third-party cookies. Cross-site requests are requests where the site (the registrable domain) and/or the scheme (http or https) do not match the site the user is currently visiting. This includes requests sent when links are clicked on other sites to navigate to your site, and any request sent by embedded third-party content. SameSite helps to prevent leakage of information, preserving user privacy and providing some protection against cross-site request forgery attacks. It takes three possible values: Strict, Lax, and None:

### 5. Assuming the following Express middleware, what would be the console.log output for an HTTP GET request with a URL path of /api/document?
req.method: The HTTP method of the request (e.g., GET, POST, PUT, DELETE).
req.path or req.route.path: The path portion of the URL that was requested (e.g., /api/document). req.path doesn’t include the domain or query string—just the route path.
req.url: The URL that was requested, including the path and any query parameters. For example, if you requested http://example.com/api/document?version=2, req.url would be /api/document?version=2.
req.originalUrl: Similar to req.url, but always refers to the original URL requested before any middleware changes. This can be useful if you have middleware that modifies the URL.

### 6. Given the following Express service code: What does the following front end JavaScript that performs a fetch return?


### 7. Given the following MongoDB query, select all of the matching documents {name:Mark}


### 8. How should user passwords be stored?
bcrypt
scrypt
Argon2

### 9. Assuming the following node.js websocket code in the back end, and the following front end websocket code, what will the front end log to the console?

### 10. What is the websocket protocol intended to provide?
full-duplex, real-time communication between clients (such as web browsers) and servers over a single, long-lived connection.

### 11. What do the following acronyms stand for? JSX, JS, AWS, NPM, NVM
JSX: JavaScript XML, JS: JavaScript, AWS: Amazon Web Service, NPM: Node Package Manager, NVM: Node Version Manager


### 12. Assuming an HTML document with a body element. What text content will the following React component generate?  
The react component will use parameters.


### 13. Given a set of React components that include each other, what will be generated


### 14. What does a React component with React.useState do?
Declares a state variable: It creates a variable that can hold and manage data within your component.
Returns a pair of values:
The first value is the current state.
The second value is a function to update the state.
Triggers re-renders: When you call the update function, it triggers React to re-render the component, reflecting the new state.

### 15. What are React Hooks used for?
React hooks are functions that let you "hook into" React features like state and lifecycle methods directly from functional components. 

### 16. What does the State Hook/Context Hook/Ref Hook/Effect Hook/Performance Hook do? https://react.dev/reference/react/hooks
Hook/Contex: Context lets a component receive information from distant parents without passing it as props. For example, your app’s top-level component can pass the current UI theme to all components below, no matter how deep.

useContext reads and subscribes to a context.
function Button() {
  const theme = useContext(ThemeContext);
  // ...

Hook/Ref: Refs let a component hold some information that isn’t used for rendering, like a DOM node or a timeout ID. Unlike with state, updating a ref does not re-render your component. Refs are an “escape hatch” from the React paradigm. They are useful when you need to work with non-React systems, such as the built-in browser APIs.

useRef declares a ref. You can hold any value in it, but most often it’s used to hold a DOM node.
useImperativeHandle lets you customize the ref exposed by your component. This is rarely used.
function Form() {
  const inputRef = useRef(null);
  // ...

Hook/Effect: Effects let a component connect to and synchronize with external systems. This includes dealing with network, browser DOM, animations, widgets written using a different UI library, and other non-React code.

useEffect connects a component to an external system.
function ChatRoom({ roomId }) {
  useEffect(() => {
    const connection = createConnection(roomId);
    connection.connect();
    return () => connection.disconnect();
  }, [roomId]);
  // ...
Effects are an “escape hatch” from the React paradigm. Don’t use Effects to orchestrate the data flow of your application. If you’re not interacting with an external system, you might not need an Effect.

There are two rarely used variations of useEffect with differences in timing:

useLayoutEffect fires before the browser repaints the screen. You can measure layout here.
useInsertionEffect fires before React makes changes to the DOM. Libraries can insert dynamic CSS here.

Hook/Performance: A common way to optimize re-rendering performance is to skip unnecessary work. For example, you can tell React to reuse a cached calculation or to skip a re-render if the data has not changed since the previous render.

To skip calculations and unnecessary re-rendering, use one of these Hooks:

useMemo lets you cache the result of an expensive calculation.
useCallback lets you cache a function definition before passing it down to an optimized component.
function TodoList({ todos, tab, theme }) {
  const visibleTodos = useMemo(() => filterTodos(todos, tab), [todos, tab]);
  // ...
}
Sometimes, you can’t skip re-rendering because the screen actually needs to update. In that case, you can improve performance by separating blocking updates that must be synchronous (like typing into an input) from non-blocking updates which don’t need to block the user interface (like updating a chart).

To prioritize rendering, use one of these Hooks:

useTransition lets you mark a state transition as non-blocking and allow other updates to interrupt it.
useDeferredValue lets you defer updating a non-critical part of the UI and let other parts update first.

### 17. Given React Router code, select statements that are true.

### 18. What does the package.json file do?
package. json is a metadata file in a Node. js project that describes the project's dependencies, scripts, configuration, and other details. It typically contains information about the project such as its name, version, author, and license. It also lists the project's dependencies on other Node

### 19. What does the fetch function do?
The fetch() method of the Window interface starts the process of fetching a resource from the network, returning a promise that is fulfilled once the response is available. The promise resolves to the Response object representing the response to your request.

### 20. What does node.js do?
it is a runtime environment allowing you to execute JavaScript code on the server side, outside a web browser.

### 21. What does pm2 do?
PM2 Runtime is a Production Process Manager for Node. js applications with a built-in Load Balancer. It allows you to keep applications alive forever, to reload them without downtime and facilitate common Devops tasks. 

### 22. What does Vite do?
Vite is a modern JavaScript build tool that primarily serves your code locally during development using native ES Modules, providing a fast development experience, and then bundles your code with Rollup for optimized production builds, essentially allowing for rapid development with quick refresh times and efficient production output; it is known for its speed and simplicity, particularly when working with frameworks like React and Vue.

