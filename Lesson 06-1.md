## Outcomes  
- Understand react router

## React router
Currently all our apps have been single page apps. What if we want multiple pages? This is where react router comes in.

React router allows us to render different pages based on our route for example 
`myapp.com/about`
`myapp.com/store`

#### Install
`$ yarn add react-router-dom@6`

#### BrowserRouter
In order to use react router we need to wrap all our routes in the BrowserRouter component

```js
import { BrowserRouter } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <h1>My awesome app</h1>
    </BrowserRouter>
  );
}
```

#### Link Components
Link components allow us to link to other routes in our app

```js
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link> | <Link to="/about">About</Link> |{" "}
        <Link to="/contact">Contact</Link>
      </nav>
      <h1>My awesome app</h1>
    </BrowserRouter>
```

#### Routes
We can tell react router what pages to display by using the routes component 

```js
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link> | <Link to="/about">About</Link> |{" "}
        <Link to="/contact">Contact</Link>
      </nav>
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </BrowserRouter>
```

#### No page found
```js
<Routes>
  <Route path="/" element={<HomePage />} />
  <Route path="/about" element={<About />} />
  <Route path="/contact" element={<Contact />} />
  <Route path="*" element={<p>Page not found</p>} />
</Routes>
```
If we add the `*` to a route it will match anything else, allowing us to have a page not found page