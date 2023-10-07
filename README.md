# JAMCraft - JAMStack CI/CD Setup (Node.js & EJS)

## 1. Introduction

This document presents the architecture of a JAMstack build setup, converting EJS and Markdown files into HTML, ensuring a streamlined Continuous Integration (CI) and Continuous Deployment (CD) through GitHub Actions.

## 2. System Overview

The system is designed to automatically convert EJS and Markdown files into HTML, facilitating content update and website management. Leveraging the JAMstack architecture, the setup uploads an artifact which can be deployed to GitHub Pages or any other static hosting service, such as Netlify, Vercel, or AWS S3.

The Front-end assets (CSS, JS) are bundled in parallel, uploaded as a separate artifact, and deployed to a separate hosting service, such as Netlify, Vercel, or AWS S3.

Media assets are processed (generate thumbnails, compress images, etc.) and uploaded to a separate hosting service, such as Netlify, Vercel, or AWS S3.

### 2.1 Objectives:

-   Generate static HTML pages from EJS and Markdown files.
-   Automated build and deployment through GitHub Actions.
-   Maintain a clean and modular structure for content, templates, and assets.
-   Ensure a streamlined CI/CD process.

## Resources

-   [Build a Static site Generator in 40 lines with Node.js](https://www.webdevdrops.com/en/build-static-site-generator-nodejs-8969ebe34b22/)

## To Do:

-   [ ] Restructure to use Component Driven Development
-   [ ] Restructure to use Atomic Design
-   [ ] Github Actions Setup CI/CD

## Possible Improvements

-   [ ] Preview Deployments:
        Generate preview deployments for pull requests to visualize changes before merging into the main codebase.

-   [ ] Asynchronous Operations:
        Consider using asynchronous operations to avoid potential blocking of the event loop with synchronous filesystem operations, especially if you scale up to process many files. Node.js has native Promises-based versions of the fs module (fs/promises) which you might find useful.

-   [ ] Error Handling:
        Error handling is crucial, especially when dealing with file operations and rendering processes. Try to wrap your file operations and rendering functions inside a try/catch block to manage errors gracefully.
  
-   [ ] Logging:
        Include logs to inform the user (or developer) about the ongoing process, e.g., which file is currently being processed, whether the file has been written successfully, etc.
  
-   [ ] Code Modularization:
        You may want to consider modularizing your code into separate functions or even files to make it cleaner and more maintainable. For instance, separate functions for handling markdown files, rendering EJS, copying assets, etc., would make the main file much cleaner and functions reusable.

-   [ ] Avoid Global Config Import:
        Instead of importing the configuration globally (const config = require('../site.config');), consider passing it as a parameter to your functions to make them more pure and predictable.

-   [ ] Extensibility:
        In the future, you might want to make the script more extensible (e.g., allowing for plugin systems for post-processors, minifiers, etc.). So, keep extensibility in mind while structuring your code.


-   [ ] Documentation:
        Consider adding some documentation to your code to make it easier for others to understand and contribute to it.

-   [ ] CLI:
        You might want to consider turning your script into a CLI tool to make it easier to use and more accessible to others.
