// NExtJs Documentation......

![alt text](1_BQZAbczBfLYtPp-6HmN0ZQ.jpg)

 Table of Content.

1. Introduction to Next.js
2. Installation
3. Building Your Application
4. Routing
5. Data Fetching
7. Rendering
8. Caching
9. Styling
10. Optimizing
11. Configuring
12. Testing
13. Authentication
14. Deploying
15. Upgrading


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

