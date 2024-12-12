## CS 260 Final Exam Questions

### What is the default port for HTTP/HTTPS/SSH? 
HTTP: 80, HTTPS: 443, SSH: 22

### What does an HTTP status code in the range of 300/400/500 indicate?
Errors 300: Redirection, 400: client errors, 500: server errors

### What does the HTTP header content-type allow you to do?
The Content-Type HTTP header (also known as media type or MIME type) is a representation header used to inform servers/browsers about the original media type of an asset before any encoding takes place[1]. The content type header contains two values – media type and subtype.

### What does a “Secure cookie”/”Http-only cookie”/”Same-site cookie” do? https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies
Secure Cookie: only sent to the server with an encrypted request over the HTTPS protocol. It's never sent with unsecured HTTP (except on localhost), which means man-in-the-middle attackers can't access it easily. Insecure sites (with http: in the URL) can't set cookies with the Secure attribute. However, don't assume that Secure prevents all access to sensitive information in cookies. For example, someone with access to the client's hard disk (or JavaScript if the HttpOnly attribute isn't set) can read and modify the information. A cookie with the Secure attribute is only sent to the server with an encrypted request over the HTTPS protocol
Http-only Cookie: can't be accessed by JavaScript, for example using Document.cookie; it can only be accessed when it reaches the server. Cookies that persist user sessions for example should have the HttpOnly attribute set — it would be really insecure to make them available to JavaScript. This precaution helps mitigate cross-site scripting (XSS) attacks.
Same-site cookie: lets servers specify whether/when cookies are sent with cross-site requests — i.e. third-party cookies. Cross-site requests are requests where the site (the registrable domain) and/or the scheme (http or https) do not match the site the user is currently visiting. This includes requests sent when links are clicked on other sites to navigate to your site, and any request sent by embedded third-party content. SameSite helps to prevent leakage of information, preserving user privacy and providing some protection against cross-site request forgery attacks. It takes three possible values: Strict, Lax, and None:

### Assuming the following Express middleware, what would be the console.log output for an HTTP GET request with a URL path of /api/document?
req.method: The HTTP method of the request (e.g., GET, POST, PUT, DELETE).
req.path or req.route.path: The path portion of the URL that was requested (e.g., /api/document). req.path doesn’t include the domain or query string—just the route path.
req.url: The URL that was requested, including the path and any query parameters. For example, if you requested http://example.com/api/document?version=2, req.url would be /api/document?version=2.
req.originalUrl: Similar to req.url, but always refers to the original URL requested before any middleware changes. This can be useful if you have middleware that modifies the URL.

### Given the following Express service code: What does the following front end JavaScript that performs a fetch return?


### Given the following MongoDB query, select all of the matching documents {name:Mark}


### How should user passwords be stored?
bcrypt
scrypt
Argon2

### Assuming the following node.js websocket code in the back end, and the following front end websocket code, what will the front end log to the console?

### What is the websocket protocol intended to provide?
full-duplex, real-time communication between clients (such as web browsers) and servers over a single, long-lived connection.

### What do the following acronyms stand for? JSX, JS, AWS, NPM, NVM
JSX: JavaScript XML, JS: JavaScript, AWS: Amazon Web Service, NPM: Node Package Manager, NVM: Node Version Manager


### Assuming an HTML document with a body element. What text content will the following React component generate?  The react component will use parameters.


### Given a set of React components that include each other, what will be generated


### What does a React component with React.useState do?


### What are React Hooks used for?


### What does the State Hook/Context Hook/Ref Hook/Effect Hook/Performance Hook do? https://react.dev/reference/react/hooks

### Given React Router code, select statements that are true.

### What does the package.json file do?

### What does the fetch function do?

### What does node.js do?

### What does pm2 do?

### What does Vite do?

