# React Routing

- We have to install a package for doing routing with name [react router](https://reactrouter.com/en/main), to install it `npm install react-router-dom`.
- With this package which we will be using, and with this package which allows us to listen to URL changes and then load different content.

### To do the routing we have multi steps process.

1. The first step, is that we must define the routes we wanna support so we must define which URLs, which path we wanna supports and which components should be loaded for different paths.
2. The second step, that is to activate our router, and load the route definitions that we defined in the first step.
3. The thirs step, is to make sure that we have all these components that we do wanna load and that we maybe also provide some means of navigating between those pages. So that our users can move smoothly between the different pages.

```
import { createBrowserRouter, RouterProvider } from "react-router-dom";
import HomePage from "./pages/Home";
import ProductsPage from "./pages/Products";

const router = createBrowserRouter([
    { path: "/", element: <HomePage /> },
    { path: "/products", element: <ProductsPage /> },
]);

function App() {
return <RouterProvider router={router} />;
}

export default App;
```

#### Exploring an Alternatibve way of defining routes

```
import {
  createBrowserRouter,
  createRoutesFromElements,
  RouterProvider,
  Route,
} from "react-router-dom";

import HomePage from "./pages/Home";
import ProductsPage from "./pages/Products";

const routeDefinitions = createRoutesFromElements(
  <Route>
    <Route path="/" element={<HomePage />} />
    <Route path="/products" element={<ProductsPage />} />
  </Route>
);

const router = createBrowserRouter(routeDefinitions);

function App() {
  return <RouterProvider router={router} />;
}

export default App;

```

#### Navigating between Pages with Links
