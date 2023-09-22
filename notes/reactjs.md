# REACT JS

## CREATE NEW APP

```bash
# basic react app
npx create-react-app my-app
cd my-app
npm start

# with vite
npm create vite@latest #choose name and pick react
cd my-app
npm install
npm run dev
```

## MINIMAL APPLICATION

```tsx
import React from "react"
import ReactDOM from "react-dom/client"

const root = ReactDOM.createRoot(document.getElementById("root"))
root.render(<React.StrictMode>Hello</React.StrictMode>)
```

## INSERTING A COMPONENT

```tsx
import React from "react"
import ReactDOM from "react-dom/client"

const MyComponent = () => {
  return (
    <>
      <h1>Welcome</h1>
      <p>Welcome to my website</p>
    </>
  )
}

const root = ReactDOM.createRoot(document.getElementById("root"))
root.render(
  <React.StrictMode>
    <MyComponent />
  </React.StrictMode>
)
```

## SEPARATING INTO FILES

```jsx
// src/index.js
import React from "react"
import ReactDOM from "react-dom/client"

import MyComponent from "./components/MyComponent"

const root = ReactDOM.createRoot(document.getElementById("root"))
root.render(
  <React.StrictMode>
    <MyComponent />
  </React.StrictMode>
)
```

```jsx
// src/components/MyComponent.js
const MyComponent = () => {
  return (
    <>
      <h1>Welcome</h1>
      <p>Welcome to my website</p>
    </>
  )
}

export default MyComponent
```

## INSTALL TAILWINDCSS
