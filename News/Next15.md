## NEXT 15 RC

### INTRODUCING

- React : Next supports React 19 RC, React Compiler, hydration error imporvements...
- Caching : fetch, GET route handlers, client navigations are no longer cached by default 
- Partial Prerendering (canary) : New Layout and Page config option for incremental adoption
- next/after (canary) : New API to execute code after a responese has finished streaming 
- create-next-app : Updated design and a new flag to enable Turbopack in local dev
- Bundling external packages (stable) : new config options for App & Pages Router


### INSTALLATION
npm install next@rc react@rc react-dom@rc


#### React Compiler

with Next 15, React Compiler is supported

npm install babel-plugin-react-compiler

toggle exprimental.reactCompiler in next.config

React Compiler is currently only possible to use in Next through Babel plugin which results in slower build time.

#### Caching


- fetch requests in Next 15 is set to 'no-store' by default in contrast to Next 14's 'force-cahce' (you can still opt-in with cache, dynamic, fetchCache options)
- GET route handlers are no longer cached by default (you can still opt-in by exporting dynamic = 'force-static') 
- Client Router Cache no longer caches Page Components by default which means that as you navigate around your app, the client will always reflect the latest data from the Page Components
 
  - important remains
  - Shared layout data won't be refetched from the server  to support partial rendering
  - history navigations will still restore from cache
  - Loading.js will remain cached for 5 minutes

#### Partial Prerendering (ppr)

- 