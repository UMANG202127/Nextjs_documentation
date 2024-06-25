// NExtJs Documentation......

![alt text](1_BQZAbczBfLYtPp-6HmN0ZQ.jpg)

 Table of Content.

1. Introduction to Next.js
2. Installation
3. Building Your Application
4. Routing
5. Data Fetching
6. Rendering
7. Caching
8. Styling
9. Optimizing
10. Configuring
11. Testing
12. Authentication
13. Deploying
14. Upgrading


1. Introduction to Next.js ......

Next.js is an open-source web development framework based on React and has gained significant popularity due to its amazing features. It is developed by Vercel and Next.js stands out for its robust capabilities, including server-side rendering(SSR) and enhanced search engine optimization (SEO). Next.js provides built-in routing, making it simple to create dynamic routes and handle navigation within your application.

In this Next.js Tutorial, we’ll learn all the basic to advanced concepts such as Routing, Data Fetching, Environment Variables, Meta Tags, Static File Serving, Pre-Rendering, etc.

Prerequisites to learn Next.js -
Before start learning NextJS you should have basic knowledge of how we shifted from JavaScript to React, after that, you can shift from React to NextJS. So you will need basic knowledge of HTML, CSS, Javascript, and React.

--Why learn Next.js?--
Next.js offers several advantages over traditional React development:

Built-in Routing and SSR: Unlike React, which lacks native routing, Next.js provides seamless routing functionality out of the box. Additionally, it supports server-side rendering, improving performance and SEO.
Faster Development: Next.js accelerates development by offering built-in features and conventions. Developers can focus on building features rather than configuring complex setups.
SEO Optimization: Next.js enhances SEO by addressing slow rendering and loading times associated with client-side rendering. Its SSR capabilities ensure that search engines can efficiently crawl and index your content.
Additionally, NextJS mitigates slow rendering and loading times inherent in client-side rendering, crucial for optimizing SEO performance. Its integration of server-side rendering out of the box enhances overall development efficiency and user experience.
These benefits make Next.js a compelling choice over ReactJS for many developers.

   --Main Features--
Some of the main Next.js features include:

Routing - A file-system based router built on top of Server Components that supports layouts, nested routing, 
          loading states, error handling, and more.
Rendering -	Client-side and Server-side Rendering with Client and Server Components. Further optimized with 
            Static and Dynamic Rendering on the server with Next.js. Streaming on Edge and Node.js runtimes.
Data Fetching -	Simplified data fetching with async/await in Server Components, and an extended fetch API for 
                request memoization, data caching and revalidation.
Styling	- Support for your preferred styling methods, including CSS Modules, Tailwind CSS, and CSS-in-JS
          Optimizations	Image, Fonts, and Script Optimizations to improve your application's Core Web Vitals 
          and User Experience.
TypeScript - Improved support for TypeScript, with better type checking and more efficient compilation, as 
             well as custom TypeScript Plugin and type checker.



2. Installation .....

System Requirements:

Node.js 18.17 or later.
macOS, Windows (including WSL), and Linux are supported.

starting a new Next.js app using create-next-app, which sets up everything automatically for you. To create a project, run:

![alt text](<Screenshot 2024-06-25 133933.png>)

On installation, we will see the following prompts:

![alt text](<Screenshot 2024-06-25 134600.png>)

After the prompts, create-next-app will create a folder with your project name and install the required dependencies.



3. Build your Application......

Next.js provides the building blocks to create flexible, full-stack web applications. The guides in Building Your Application explain how to use these features and how to customize your application's behavior.

The sections and pages are organized sequentially, from basic to advanced, so you can follow them step-by-step when building your Next.js application. However, you can read them in any order or skip to the pages that apply to your use case.

If you're new to Next.js, we recommend starting with the Routing, Rendering, Data Fetching and Styling sections, as they introduce the fundamental Next.js and web concepts to help you get started. Then, you can dive deeper into the other sections such as Optimizing and Configuring. Finally, once you're ready, checkout the Deploying and Upgrading sections.



4. Routing......

![alt text](<Screenshot 2024-06-25 143558.png>)
- Tree: A convention for visualizing a hierarchical structure. For example, a component tree with parent and 
        children components, a folder structure, etc.
- Subtree: Part of a tree, starting at a new root (first) and ending at the leaves (last).
- Root: The first node in a tree or subtree, such as a root layout.
- Leaf: Nodes in a subtree that have no children, such as the last segment in a URL path.

![alt text](<Screenshot 2024-06-25 143740.png>)
URL Segment: Part of the URL path delimited by slashes.
URL Path: Part of the URL that comes after the domain (composed of segments).

-- The app Router --

In version 13, Next.js introduced a new App Router built on React Server Components, which supports shared layouts, nested routing, loading states, error handling, and more.

The App Router works in a new directory named app. The app directory works alongside the pages directory to allow for incremental adoption. This allows you to opt some routes of your application into the new behavior while keeping other routes in the pages directory for previous behavior.

Roles of Folders and Files----
Next.js uses a file-system based router where:

Folders: are used to define routes. A route is a single path of nested folders, following the file-system 
         hierarchy from the root folder down to a final leaf folder that includes a page.js file. See 
         Defining Routes.
Files: are used to create UI that is shown for a route segment. See special files.

File Conventions-----
Next.js provides a set of special files to create UI with specific behavior in nested routes:

layout:	       Shared UI for a segment and its children
page:	       Unique UI of a route and make routes publicly accessible
loading:       Loading UI for a segment and its children
not-found:     Not found UI for a segment and its children
error:	       Error UI for a segment and its children
global-error:  Global Error UI
route:	       Server-side API endpoint
template:	   Specialized re-rendered Layout UI
default:	   Fallback UI for Parallel Routes


Pages and Layout ----

Pages: A page is UI that is unique to a route. You can define a page by default exporting a component from a 
       page.js file.

  For example, to create your index page, add the page.js file inside the app directory:
![alt text](<Screenshot 2024-06-25 151050.png>)

![alt text](<Screenshot 2024-06-25 151146.png>)

Then, to create further pages, create a new folder and add the page.js file inside it. For example, to create a page for the /dashboard route, create a new folder called dashboard, and add the page.js file inside it:
![alt text](<Screenshot 2024-06-25 151230.png>)


Layouts: A layout is UI that is shared between multiple routes. On navigation, layouts preserve state, remain 
         interactive, and do not re-render. Layouts can also be nested.

You can define a layout by default exporting a React component from a layout.js file. The component should accept a children prop that will be populated with a child layout (if it exists) or a page during rendering.

For example, the layout will be shared with the /dashboard and /dashboard/settings pages:
![alt text](<Screenshot 2024-06-25 151507.png>)

![alt text](<Screenshot 2024-06-25 151624.png>)


How Routing and Navigation Works----

The App Router uses a hybrid approach for routing and navigation. On the server, your application code is automatically code-split by route segments. And on the client, Next.js prefetches and caches the route segments. This means, when a user navigates to a new route, the browser doesn't reload the page, and only the route segments that change re-render - improving the navigation experience and performance.

1. Code Splitting
Code splitting allows you to split your application code into smaller bundles to be downloaded and executed by the browser. This reduces the amount of data transferred and execution time for each request, leading to improved performance.

Server Components allow your application code to be automatically code-split by route segments. This means only the code needed for the current route is loaded on navigation.

2. Prefetching
Prefetching is a way to preload a route in the background before the user visits it.

There are two ways routes are prefetched in Next.js:

<Link> component: Routes are automatically prefetched as they become visible in the user's viewport. Prefetching happens when the page first loads or when it comes into view through scrolling.
router.prefetch(): The useRouter hook can be used to prefetch routes programmatically.
The <Link>'s default prefetching behavior (i.e. when the prefetch prop is left unspecified or set to null) is different depending on your usage of loading.js. Only the shared layout, down the rendered "tree" of components until the first loading.js file, is prefetched and cached for 30s. This reduces the cost of fetching an entire dynamic route, and it means you can show an instant loading state for better visual feedback to users.

You can disable prefetching by setting the prefetch prop to false. Alternatively, you can prefetch the full page data beyond the loading boundaries by setting the prefetch prop to true.

See the <Link> API reference for more information.

Good to know:

Prefetching is not enabled in development, only in production.
3. Caching
Next.js has an in-memory client-side cache called the Router Cache. As users navigate around the app, the React Server Component Payload of prefetched route segments and visited routes are stored in the cache.

This means on navigation, the cache is reused as much as possible, instead of making a new request to the server - improving performance by reducing the number of requests and data transferred.

Learn more about how the Router Cache works and how to configure it.

4. Partial Rendering
Partial rendering means only the route segments that change on navigation re-render on the client, and any shared segments are preserved.

For example, when navigating between two sibling routes, /dashboard/settings and /dashboard/analytics, the settings and analytics pages will be rendered, and the shared dashboard layout will be preserved.

5. Soft Navigation
Browsers perform a "hard navigation" when navigating between pages. The Next.js App Router enables "soft navigation" between pages, ensuring only the route segments that have changed are re-rendered (partial rendering). This enables client React state to be preserved during navigation.

6. Back and Forward Navigation
By default, Next.js will maintain the scroll position for backwards and forwards navigation, and re-use route segments in the Router Cache.

7. Routing between pages/ and app/
When incrementally migrating from pages/ to app/, the Next.js router will automatically handle hard navigation between the two. To detect transitions from pages/ to app/, there is a client router filter that leverages probabilistic checking of app routes, which can occasionally result in false positives. By default, such occurrences should be very rare, as we configure the false positive likelihood to be 0.01%. This likelihood can be customized via the experimental.clientRouterFilterAllowedRate option in next.config.js. It's important to note that lowering the false positive rate will increase the size of the generated filter in the client bundle.

Alternatively, if you prefer to disable this handling completely and manage the routing between pages/ and app/ manually, you can set experimental.clientRouterFilter to false in next.config.js. When this feature is disabled, any dynamic routes in pages that overlap with app routes won't be navigated to properly by default.


Error Handling----

The error.js file convention allows you to gracefully handle unexpected runtime errors in nested routes.

-Automatically wrap a route segment and its nested children in a React Error Boundary.
-Create error UI tailored to specific segments using the file-system hierarchy to adjust granularity.
-Isolate errors to affected segments while keeping the rest of the application functional.
-Add functionality to attempt to recover from an error without a full page reload.

Create error UI by adding an error.js file inside a route segment and exporting a React component:
![alt text](<Screenshot 2024-06-25 152144.png>)

![alt text](<Screenshot 2024-06-25 152214.png>)

How error.js Works---

![alt text](<Screenshot 2024-06-25 152305.png>)

- error.js automatically creates a React Error Boundary that wraps a nested child segment or page.js 
  component.
- The React component exported from the error.js file is used as the fallback component.
- If an error is thrown within the error boundary, the error is contained, and the fallback component is 
  rendered.
- When the fallback error component is active, layouts above the error boundary maintain their state and - -- 
- remain interactive, and the error component can display functionality to recover from the error.

Recovering From Errors---
The cause of an error can sometimes be temporary. In these cases, simply trying again might resolve the issue.

An error component can use the reset() function to prompt the user to attempt to recover from the error. When executed, the function will try to re-render the Error boundary's contents. If successful, the fallback error component is replaced with the result of the re-render.
![alt text](<Screenshot 2024-06-25 152545.png>)


Intercepting Routes----

Intercepting routes allows you to load a route from another part of your application within the current layout. This routing paradigm can be useful when you want to display the content of a route without the user switching to a different context.

For example, when clicking on a photo in a feed, you can display the photo in a modal, overlaying the feed. In this case, Next.js intercepts the /photo/123 route, masks the URL, and overlays it over /feed.

![alt text](<Screenshot 2024-06-25 152900.png>)


Middleware -----
Middleware allows you to run code before a request is completed. Then, based on the incoming request, you can modify the response by rewriting, redirecting, modifying the request or response headers, or responding directly.

Middleware runs before cached content and routes are matched. See Matching Paths for more details.

Use Cases:
Integrating Middleware into your application can lead to significant improvements in performance, security, and user experience. Some common scenarios where Middleware is particularly effective include:

-Authentication and Authorization: Ensure user identity and check session cookies before granting access to 
 specific pages or API routes.
-Server-Side Redirects: Redirect users at the server level based on certain conditions (e.g., locale, user 
 role).
-Path Rewriting: Support A/B testing, feature rollouts, or legacy paths by dynamically rewriting paths to API 
 routes or pages based on request properties.
-Bot Detection: Protect your resources by detecting and blocking bot traffic.
-Logging and Analytics: Capture and analyze request data for insights before processing by the page or API.
-Feature Flagging: Enable or disable features dynamically for seamless feature rollouts or testing.

Recognizing situations where middleware may not be the optimal approach is just as crucial. Here are some 
scenarios to be mindful of:

-Complex Data Fetching and Manipulation: Middleware is not designed for direct data fetching or manipulation, 
 this should be done within Route Handlers or server-side utilities instead.
-Heavy Computational Tasks: Middleware should be lightweight and respond quickly or it can cause delays in 
 page load. Heavy computational tasks or long-running processes should be done within dedicated Route 
  Handlers.
-Extensive Session Management: While Middleware can manage basic session tasks, extensive session management 
 should be managed by dedicated authentication services or within Route Handlers.
-Direct Database Operations: Performing direct database operations within Middleware is not recommended. 
 Database interactions should done within Route Handlers or server-side utilities.



5. Data Fetching .......

-Fetching Data on the Server with fetch:

Next.js extends the native fetch Web API to allow you to configure the caching and revalidating behavior for each fetch request on the server. React extends fetch to automatically memoize fetch requests while rendering a React component tree.

You can use fetch with async/await in Server Components, in Route Handlers, and in Server Actions.

For example:
![alt text](<Screenshot 2024-06-25 171245.png>)

Good to know:

-Next.js provides helpful functions you may need when fetching data in Server Components such as cookies and 
 headers. These will cause the route to be dynamically rendered as they rely on request time information.
-In Route handlers, fetch requests are not memoized as Route Handlers are not part of the React component 
 tree.
-In Server Actions, fetch requests are not cached (defaults cache: no-store).
-To use async/await in a Server Component with TypeScript, you'll need to use TypeScript 5.1.3 or higher and 
 @types/react 18.2.8 or higher.




6. Rendering .....

Rendering converts the code you write into user interfaces. React and Next.js allow you to create hybrid web applications where parts of your code can be rendered on the server or the client. This section will help you understand the differences between these rendering environments, strategies, and runtimes.

Fundamentals:
To start, it's helpful to be familiar with three foundational web concepts:

-The Environments your application code can be executed in: the server and the client.
-The Request-Response Lifecycle that's initiated when a user visits or interacts with your application.
-The Network Boundary that separates server and client code.

Rendering Environments:
There are two environments where web applications can be rendered: the client and the server.

- The client refers to the browser on a user's device that sends a request to a server for your application 
  code. It then turns the response from the server into a user interface.
- The server refers to the computer in a data center that stores your application code, receives requests 
  from a client, and sends back an appropriate response.


Server Components:

React Server Components allow you to write UI that can be rendered and optionally cached on the server. In Next.js, the rendering work is further split by route segments to enable streaming and partial rendering, and there are three different server rendering strategies:

- Static Rendering
- Dynamic Rendering
- Streaming

Static Rendering (Default):
With Static Rendering, routes are rendered at build time, or in the background after data revalidation. The result is cached and can be pushed to a Content Delivery Network (CDN). This optimization allows you to share the result of the rendering work between users and server requests.

Dynamic Rendering:
With Dynamic Rendering, routes are rendered for each user at request time.
Dynamic rendering is useful when a route has data that is personalized to the user or has information that can only be known at request time, such as cookies or the URL's search params.

Streaming:
Streaming enables you to progressively render UI from the server. Work is split into chunks and streamed to the client as it becomes ready. This allows the user to see parts of the page immediately, before the entire content has finished rendering.

Client Component:

Client Components allow you to write interactive UI that is prerendered on the server and can use client JavaScript to run in the browser.
To use Client Components, you can add the React "use client" directive at the top of a file, above your imports.
"use client" is used to declare a boundary between a Server and Client Component modules. This means that by defining a "use client" in a file, all other modules imported into it, including child components, are considered part of the client bundle.

![alt text](<Screenshot 2024-06-25 172258.png>)



7. Caching.......

Next.js improves your application's performance and reduces costs by caching rendering work and data requests. This page provides an in-depth look at Next.js caching mechanisms, the APIs you can use to configure them, and how they interact with each other.

By default, Next.js will cache as much as possible to improve performance and reduce cost. This means routes are statically rendered and data requests are cached unless you opt out. The diagram below shows the default caching behavior: when a route is statically rendered at build time and when a static route is first visited.

![alt text](<Screenshot 2024-06-25 172534.png>)

Caching behavior changes depending on whether the route is statically or dynamically rendered, data is cached or uncached, and whether a request is part of an initial visit or a subsequent navigation. Depending on your use case, you can configure the caching behavior for individual routes and data requests.



8. Styling ......

Next.js supports different ways of styling your application, including:

-Global CSS: Simple to use and familiar for those experienced with traditional CSS, but can lead to larger 
 CSS bundles and difficulty managing styles as the application grows.

-CSS Modules: Create locally scoped CSS classes to avoid naming conflicts and improve maintainability.

-Tailwind CSS: A utility-first CSS framework that allows for rapid custom designs by composing utility 
 classes.

-Sass: A popular CSS preprocessor that extends CSS with features like variables, nested rules, and mixins.

-CSS-in-JS: Embed CSS directly in your JavaScript components, enabling dynamic and scoped styling.



9. Optimizations ......

Next.js comes with a variety of built-in optimizations designed to improve your application's speed and Core Web Vitals. This guide will cover the optimizations you can leverage to enhance your user experience.

Built-in Components:

Built-in components abstract away the complexity of implementing common UI optimizations. These components are:

Images: Built on the native <img> element. The Image Component optimizes images for performance by lazy 
        loading and automatically resizing images based on device size.

Link: Built on the native <a> tags. The Link Component prefetches pages in the background, for faster and 
      smoother page transitions.

Scripts: Built on the native <script> tags. The Script Component gives you control over loading and execution 
         of third-party scripts.

Metadata:
Metadata helps search engines understand your content better (which can result in better SEO), and allows you to customize how your content is presented on social media, helping you create a more engaging and consistent user experience across various platforms.

Static Assets:
Next.js /public folder can be used to serve static assets like images, fonts, and other files. Files inside /public can also be cached by CDN providers so that they are delivered efficiently.

Analytics and Monitoring:
For large applications, Next.js integrates with popular analytics and monitoring tools to help you understand how your application is performing. Learn more in the OpenTelemetry and Instrumentation guides.



10. Configuring ......

Next.js allows you to customize your project to meet specific requirements. This includes integrations with TypeScript, ESlint, and more, as well as internal configuration options such as Absolute Imports and Environment Variables.

- TypeScript:
  Next.js provides a TypeScript-first development experience for building your React application.

- ESLint:
  Next.js provides an integrated ESLint experience by default. These conformance rules help you use Next.js 
  in an optimal way.

- Environment Variables:
  Learn to add and access environment variables in your Next.js application.

- Absolute Imports and Module Path Aliases:
  Configure module path aliases that allow you to remap certain import paths.  

- src Directory:
  Save pages under the `src` directory as an alternative to the root `pages` directory.

- Draft Mode:
  Next.js has draft mode to toggle between static and dynamic pages. You can learn how it works with App 
  Router.



11. Testing .......

In React and Next.js, there are a few different types of tests you can write, each with its own purpose and use cases. This page provides an overview of types and commonly used tools you can use to test your application.

Types of tests:

- Unit testing involves testing individual units (or blocks of code) in isolation. In React, a unit can be a 
  single function, hook, or component.

- Component testing is a more focused version of unit testing where the primary subject of the tests is React 
  components. This may involve testing how components are rendered, their interaction with props, and their 
  behavior in response to user events.

- Integration testing involves testing how multiple units work together. This can be a combination of 
  components, hooks, and functions.

- End-to-End (E2E) Testing involves testing user flows in an environment that simulates real user scenarios, 
  like the browser. This means testing specific tasks (e.g. signup flow) in a production-like environment.

- Snapshot testing involves capturing the rendered output of a component and saving it to a snapshot file. 
  When tests run, the current rendered output of the component is compared against the saved snapshot. 
  Changes in the snapshot are used to indicate unexpected changes in behavior.


Setting up Playwright with Next.js:

Playwright is a testing framework that lets you automate Chromium, Firefox, and WebKit with a single API. You can use it to write End-to-End (E2E) testing. This guide will show you how to set up Playwright with Next.js and write your first tests.

Manual setup
To install Playwright, run the following command:
![alt text](<Screenshot 2024-06-25 174324.png>)

Running your Playwright tests
Playwright will simulate a user navigating your application using three browsers: Chromium, Firefox and Webkit, this requires your Next.js server to be running. We recommend running your tests against your production code to more closely resemble how your application will behave.

Run 'npm run build' and 'npm run start', then run npx playwright test in another terminal window to run the Playwright tests.




12. Authentication .......


Authentication verifies a user's identity. This happens when a user logs in, either with a username and password or through a service like Google. It's all about confirming that users are really who they claim to be, protecting both the user's data and the application from unauthorized access or fraudulent activities.

Authentication Strategies:
Modern web applications commonly use several authentication strategies:

- OAuth/OpenID Connect (OIDC): Enable third-party access without sharing user credentials. Ideal for social 
  media logins and Single Sign-On (SSO) solutions. They add an identity layer with OpenID Connect.

- Credentials-based login (Email + Password): A standard choice for web applications, where users log in with 
  an email and password. Familiar and easy to implement, it requires robust security measures against threats 
  like phishing.

- Passwordless/Token-based authentication: Use email magic links or SMS one-time codes for secure, password- 
  free access. Popular for its convenience and enhanced security, this method helps reduce password fatigue. 
  Its limitation is the dependency on the user's email or phone availability.

- Passkeys/WebAuthn: Use cryptographic credentials unique to each site, offering high security against 
  phishing. Secure but new, this strategy can be difficult to implement.

Selecting an authentication strategy should align with your application's specific requirements, user interface considerations, and security objectives.

Implementing Authentication:

In this section, we'll explore the process of adding basic email-password authentication to a web application. While this method provides a fundamental level of security, it's worth considering more advanced options like OAuth or passwordless logins for enhanced protection against common security threats. The authentication flow we'll discuss is as follows:

1. The user submits their credentials through a login form.

2. The form calls a Server Action.

3. Upon successful verification, the process is completed, indicating the user's successful authentication.

4. If verification is unsuccessful, an error message is shown.

Consider a login form where users can input their credentials:
![alt text](<Screenshot 2024-06-25 174919.png>)

The form above has two input fields for capturing the user's email and password. On submission, it calls the authenticate Server Action.

You can then call your Authentication Provider's API in the Server Action to handle authentication:

![alt text](<Screenshot 2024-06-25 174957.png>)

In this code, the signIn method checks the credentials against stored user data. After the authentication provider processes the credentials, there are two possible outcomes:

- Successful Authentication: This outcome implies that the login was successful. Further actions, such as 
  accessing protected routes and fetching user information, can then be initiated.
- Failed Authentication: In cases where the credentials are incorrect or an error is encountered, the 
  function returns a corresponding error message to indicate the authentication failure.

Finally, in your login-form.tsx component, you can use React's useFormState to call the Server Action and handle form errors, and use useFormStatus to handle the pending state of the form:
![alt text](<Screenshot 2024-06-25 175133.png>)




13. Deploying ......

Deploying
Congratulations, it's time to ship to production.

You can deploy managed Next.js with Vercel, or self-host on a Node.js server, Docker image, or even static HTML files. When deploying using next start, all Next.js features are supported.

Production Builds:

Running next build generates an optimized version of your application for production. HTML, CSS, and JavaScript files are created based on your pages. JavaScript is compiled and browser bundles are minified using the Next.js Compiler to help achieve the best performance and support all modern browsers.

Next.js produces a standard deployment output used by managed and self-hosted Next.js. This ensures all features are supported across both methods of deployment. In the next major version, we will be transforming this output into our Build Output API specification.

Self-Hosting....

You can self-host Next.js in three different ways:

A Node.js server
A Docker container
A static export


