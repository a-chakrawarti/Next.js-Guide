# NextJs Introduction

## Documentation: https://nextjs.org/docs/getting-started

Next.js is a wrapper around react framework which enables your react code to pre-render on the server.

- In react, the server sends you javascript bundles which is ran by the client.

- Next.js on the other hand does pre-rendering, that is server side rendering of react code. The server sends html instead of sending javascript bundles.

## Installing NextJS

1. `npx create-next-app <app-name> --use-npm`
2. Change `.js` files into `.tsx`.
3. Create a `tsconfig.json` in project root directory.
4. Now to add support for typescript install the module, `npm i typescript --save-dev`
5. Install type definitions as well of node and react, `npm i @types/node @types/react --save-dev`
6. `--save-dev` is a flag install these on for development purpose, will not be carried to the production.
7. `npm run dev` : Will handle everything required to start the project, typescript, hot reload and everything.

## File Structure

- Whatever is placed in the `public` folder, that will be directly accessable in the form of raw source in the root domain.
- `pages` directory is the heart of the application.
- Content/files with-in `styles` directory can be moved to `pages` folder. And get rid of the `styles` folder.
- You must have 2 folders, `public` for static assets and `pages` folder for source code. `pages` folder can be moved to `src` folder.

## Pages

- Provides powerful yet simple routing mechanism.
- The files with `ts`, `tsx`, `js`, `jsx` extensions within the pages, it will create a path to that file and return that component to the browser, expect `index.tsx`.
- Being able to return static html, is much faster compared to react as one doesn't have to wait for any JS to execute. Which increases the performance a lot for the client side.
- Any component within the `pages` directory should export a react component as a default export.

## \_document.tsx

- It is not a component, it is the actual document that is being rendered and is used to create overall structure.
- The JS code in this file is never executed on the client side.
- Helps in injecting our own custom code/scripts which we want that to be available for the whole application.
- Use this as minimal as you can
- This is a root file for the whole application so don't mess it up a lot.

## \_app.tsx

- It is responsible for rendering all the pages.
- The function is executed both in the server side as well as in the client side.
