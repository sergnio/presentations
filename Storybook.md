## Storybook

## Presentation setup
1. Slides from slides.com
2. Giotransit running locally
3. Giotransit SB running locally
4. Sapphire app (dev)
5. Sapphire SB running locally

### Agenda
1. Show an existing app & flow
2. Explain storybook, high level
3. Dive deep into examples of storybook
4. Storybook helps with testing, writing simple, clean, resuable code
5. SB can help with Sapphire
6. Downsides
7. Conlusions
8. Questions

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

That's really all this app does, but if I make a change to the table component, say, I add some text in the table and want to validate it shows up, I'm going to have to go through the exercise of choosing every option to get there  
And of course, this is a silly little example, but when you're doing something in Sapphire like: trying to test out some functionality in audiences  

1. you might need to create a new test  
2. create a name, choose your channel
3. choose which experiment type you want to run
4. choose a team
5. define a primary metric
6. choose an expected change
7. state your hypothesis if, then, due to statements 
8. now finally you're at the Design page where you can click the button to add an audience  
If you're smart, you can have several tests in different states of the app, but I think we can do one better

Instead of doing that, what if there was a unique tool that only currently exists for web that we're super lucky to have available to us?

### What is storybook? (high level)
* show some slide here w/ gif *
Library which allows you to do isolated component development where you can put your components into different states 
and switch between them to help make it easier to develop without spinning up your entire application - and more which we'll get to

### How might you (visually) test something that you've written?
* show arrow button *  
A nice example is you're testing this arrow button, and it has several states depending on some data based off a live test  
and you're new to the team so you actually don't know how to get them into all these states, other than hard coding them
so you just create a story to test them and see if they're in all the states you expect!  
which I'll get to later  

### How can you change the states?
Storybook will automatically create these controls, based on the props of that component  
Let's look at the button component
Otherwise, you can create separate stories to explicitly control the states of the component

### But I can just do all of this running the app...

### How might you (programatically) test a story?

### How is storybook better than just creating tests for each state it should be?
It's all visual, so it's so much easier to see things in different states  
and once you visually reproduce the component in a different state, you can just use THAT story in your test  
Also, when you're writing that annoying unit test and are having a hard time understanding what's actually being rendered, this should occur less if you've written a storybook story for that state you're trying to test  
You can do that in cypress and it's incredible to see, but as we've seen cypress can be really flaky, so we can get the benefits of being able to visually see our tests while still being able to unit test this, and not needing to write cypress tests

### Better component hierarchy, less nesting, less dependencies
* show example of how it can be a struggle bus, with that "validation story" *

### But what about mocks?

### Reusable mocks??

### What about Sapphire?

### Simple component

### Sana can use this
It's similar to the ephermerals where sana can come in here without a dev env, but the cool thing is Sana can see the exact states of things (like the benefit we get from it) without needing to jump through a bunch of hoops to do so

### And redux?

### The downsides?

### More maintenance
You now have to maintain each story, and since it heavily relies on being mocked, any changes can break stories 

### New library syntax?
You'll have to learn how to automatically add knobs, maybe you want to change something to a slider instead of manually inputting a number, so it's one more thing to learn

### Sapphire has A LOT of nested components
If we start to use SB, we need to start from the simplest of the simple and work our way up since there are so many dependencies so value won't be immediately realized

### Conclusion
As with any library or framework, they should just be tools to improve your code and your developer experience. If we find that something like storybook is just slowing us down and creating more headaches, it's not worth bringing it in as that would obviously be counter intuitive  
That being said, I've found it a great addition to my projects, and a way to simplify your life when testing
