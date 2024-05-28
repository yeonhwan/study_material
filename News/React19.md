## REACT 19 RC


### New Features

#### INTRODUCING

- Actions are supported in useTransition.
- <form>, <button>, <input> supports action, formAction
- useActionState 
- useFormStatus 
- useOptimistic
- use (new API)
- Server Components
- Server Actions
- React Compiler

#### IMPORVED

- 'ref' as a prop (no longer need to use forwardRef)
- Diffs error on hydration show once not multiple
- <Context> as a provider (no longer need to use <Context.Provider>)
- cleanup functions for 'refs' (no longer support implicit return of 'ref' function)
- 'useDeferredValue' has now opt initial value
- support for Document Metadata, now you can embed metadata tag in components natively.
- support for stylesheets, you can set 'precedence' prop to stylesheets and it will be loaded as its order not with the order of the rendering (one with the higher precedence goes later, because CSS prioritize latest styles)
- support for async scripts, async scripts in Component will be managed and deduplicated in rerendering process.
- support for preloading resources, React19 introduces new APIs such as preinit, preload, prefetch, preconnect...to control Browser's preloading events. These APIs can be used also with events like click / hover.
- improved compatibility for third-party-scripts with hydration.
- better error reporting, not multiple and duplicated. (ErrorBoundary)
- full supports for Custom Elements (Web Components)

### Concepts

#### 1. Actions


Now 'useTransition' hooks accepts async function as a callback for startTransition function to set pending state according to its async event.

By convention This async callback transition is called 'Action'.

Actions automatically manage submitting data for you.
- pending state
- optimistic updates : actions are now also supported with 'useOptimistc' hook
- error handling
- Forms : <form> elements now support passing functions to the 'action' and 'formAction' props. Passing functiosn to the 'action' props use Actions by default and reset the form automatically after submission. => 'react-dom' packages introduces a new <form action formAction> element and hook called 'useFormStatus'.

in regards of Actions, React introduces a new hook called 'useActionState' to handle comman cases for Actions. 

<code>
const [state, formAction] = useActionState(async (fn, initialState, permalink?) => {...})
</code>

'useActionState' accepts a function(Action) and returns a wrapped Action to call(submitAction).
useActionState will return the last result of the Action as data and the pending state of the Actions as pending.

'useActionState' was previously called as 'useFormStatus'

We’ve added support for passing functions as the action and formAction props of <form>, <input>, and <button> elements to automatically submit forms with Actions:

#### 2. use


#### 3. Server Components


#### 4. Server Actions

#### 5. React Compiler

### Upgrade Guide

Now stable React latest version is 18.3(react@18.3) to help better migration to 19 (identical to 18.2 but adds warnings for deprecated API in 19)


#### Installation

1. npm install react@rc react-dom@rc

1-1. if youre using Typescript, you have to update types@react version until React 19 is stable.

2. Automatic migration for deprecated API's is possible by using codemod 'npx codemod@latest react/19/migration-recipe'.



### React Conf 2024


#### Day1

React Dom & React 19 Releases

 - React 19 & Server Components
 - React Compilers
 - React Router 7 

#### Day2

React Native & its new architecture


#### React Q&A and more

- accessibility
- CSS in server components
- Server Components
- React Rules
- errors




