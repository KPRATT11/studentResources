<!-- @format -->

# Week 2 - Part 1

## Outcomes  
- Using state with inputs
- Work with more complex state information  

## Storing inputs in react 
When it comes to inputs and their values it is a good idea to store them in state. for this example lets use the mini-twitter app we created in class 

```js
class MiniTwitter extends Component {
  state = {
    tweets: startingTweets,
  };

  handlePost = () => {
    // How do we know what the value of the text box is?
  };

  render() {
    return (
      <div>
        <input type="text" />
        <br />
        <button onClick={this.handlePost}>Post</button>
        {this.state.tweets.map((tweet, index) => {
          return (
            <Tweet
              key={index}
              username={tweet.username}
              content={tweet.content}
            ></Tweet>
          );
        })}
      </div>
    );
  }
}
```

as you can see above in the handlePost function we need to find a way to get the value of the input so that we can use it when creating a post 

for this we can create an element in state

```js
  state = {
    tweets: startingTweets,
    newTweet: "",
  };
```

we can now hook up our input value to the state by using the on change event 

```js
<input type="text" onChange={this.handleInputChange} />
```

there is still an issue, when we type in our input nothing shows up, this is because we havent actually told our input element what value to use we can do this by doing 

```js
<input type="text" value={'New Tweet'} onChange={this.handleInputChange} />
```

Now that we have the value set in our state we can use it whenever we want, for example creating a new tweet

```js
handlePost = () => {
  const tweets = this.state.tweets;
  const newTweet = {
    username: "Joe",
    content: this.state.newTweet,
  };
  this.setState({
    tweets: [newTweet, ...tweets], // Add the new tweet to the beginning of the array
    newTweet: "", // Reset to blank after posting.
  });
};
```
