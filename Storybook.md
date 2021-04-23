## Storybook

### Deep dive
Lets start by showing the simple bus route app which calls the metro transit API  
See that's it's a pretty simple app overall, with several moving parts  
Let's just look at this component by component:
- Header
- First dropdown
- Second and third dropdown
- Table

Not that complicated of an app, but one reason I think this is a nice example app is because the app can be in several states  
Assuming the happy path, the major states of this app are

1. Base case: first dropdown populated 
2. First dropdown has a choice, populate the buttons
3. Second button is chosen, populate 2nd dropdown
4. Second dropdown has a choice, populate the table

That's really all this app does, but if I make a change to the third dropdown, say, I append the index+1 before each of the  
text in the autocomplete component, I'm going to have to go through the exercise of choosing the first two options

Instead of doing that, what if there was a unique tool that only currently exists for web that we're super lucky to have available  
to us?

### What is storybook? (high level)
Isolated component development where you can put your components into different states 
and switch between them to help make it easier to develop without spinning up your entire application

### How can you change the states?

### But what about testing?

### But what about mocks?

### What about Sapphire?

### Simple component

### And redux?
