## Outcomes
- Understand the importance of accessability and how to implement it in our react apps

## Semantic Structure 
One big mistake many developers do is using the `<div>` for everything, while this works on a technical level it makes it very difficult for screen readers and other accesability apps to understand the structure of our app. Instead of just using `<div>` see if there might be a more appriopriate html tag for your intended use case

## Accessible forms
Html forms are already accessible and allow for tabbing between elements on the form, becuase of this it is important that we use the form elements correctly when creating forms for our site.

```js
function GoodForm1() {
  return (
    <>
      <form>
        <h2>Shipping information</h2>
        <label htmlFor="address">Enter your address:</label>
        <br />
        <input
          id="address"
          name="address"
          autoComplete="street-address"
          required
        />
        <button>Submit</button>
      </form>
    </>
  );
}
```
## Mouse events 
We often have many actions within our apps that utilize mouse events, however this can cause issue for users with screen readers or other accessability needs. It is important to consider how we might go about adressing these issues 

for example lets say that we have a modal that gets popped up on click

```js
function PopUp() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div>
      <p>
        <a href="#">Focus before</a>
      </p>

      <div
        hidden={!isOpen}
        className="popup-content"
        onMouseLeave={() => setIsOpen(false)}
      >
        <p>Extra info here!</p>
      </div>

      <button onClick={() => setIsOpen(true)}>More info</button>

      <p>
        <a href="#">Focus after</a>
      </p>
    </div>
  );
```

This works well for people using a mouse but those who are not will be unable to focus on the modal pop up

In order to set focus to an element programtically we need to get the dom input of that element 

```js
const dialog = useRef(null);
```

We also need to add tabindex="0" to make it so that the <div> is focus-able at all! (Or it won't work!)

```js 
<div ref={dialog} tabindex="0" hidden={!isOpen} className="popup-content">
  <p>Extra info here!</p>
</div>

```

This is to ensure that even if the element gets replaced during a re-render, we'll still have a valid reference to the DOM Element.

We can use dialog.current to get the DOM element, and dialog.current.focus() to get the browser to focus on it through code.

```js
 useEffect(() => {
    if (isOpen) {
      dialog.current.focus();
    }
  }, [isOpen]);
```

Ok, it has focus when it opens now (see the blue outline?), so what about closing the popup?

Since we're using focus, we can also detect when the focus leaves the popup as well. It's called blur, it's particularly useful for textboxes if you want something to happen when the textbox has focus and then again when it loses focus.

```js
      <div
        ref={dialog}
        tabindex="0"
        hidden={!isOpen}
        className="popup-content"
        onBlur={() => setIsOpen(false)}
      >
        <p>Extra info here!</p>
      </div>
```