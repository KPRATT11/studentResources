## Outcomes
Understand how to use nested routes in react router

## Nested routes
Nested routes allow us to create more complex routes, for example I can have a products route at `/products` and I can have a route for a specific product at `/products/{product:id}` 

#### Nested route links 
Making a link for a nested route is simple 
```js
<Link to={`/products/${product.id}`}>{product.name}</Link>
```

#### Nested routes using the route component 
We can then make react router use this nested routes by nesting them as a child inside of our routes component 

```js 
  <Route path="/products" element={<Products />}>
    <Route path=":productID" element={<p>Individual product page?</p>} />
  </Route>
```