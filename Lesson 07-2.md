## Outcomes
- Understand the value in writing unit tests
- Be able to write simple unit tests for React components with Jest
- Mock out fetch calls for testing
- Test components that use ReactRouter

## Creating tests
normally tests are placed in a file simillarly named to the file we are testing but with a .test extentension 

for example if we had `Button.js` we would call the file `Button.test.js`

#### Test Function
All of our tests will be inside the test function

```js
test("title", () => {
  render(<Button />);
});
```
the renders method renders whatever component we provide, this allows us to test what the user will see on the screen

```js
test("renders text", () => {
  render(<Button />);

  const text = screen.getByText("Defualt button text");
  expect(text).toBeInTheDocument();
});
```

We can use the expect method to actually test functionality here we are testing that the text actually shows up in the document when we render out component 

```js
test("renders text provided as a prop", () => {
  render(<Button text="Different Text"/>);

  const text = screen.getByText("Different Text");
  expect(text).toBeInTheDocument();
});
```

We can also provide props to components to ensure that the component behaves as expected when certain props are passed

#### ways to query elements 
Sometimes we are unable to query elements by text, fortunetly react testing library gives us a few ways we can query the elements 

`ByRole` This can be used to query every element that is exposed in the accessibility tree.

`ByLabelText` This method is really good for form fields. When navigating through a website form, users find elements using label text.

`ByPlaceholderText` While a label is more preferable this can be better for feilds where there is no label 

`ByText` Outside of forms, text content is the main way users find elements. This method can be used to find non-interactive elements (like divs, spans, and paragraphs).

`ByTestId` This should be used as a last resort it allows you to query components that have