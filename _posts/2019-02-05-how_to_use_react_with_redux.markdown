---
layout: post
title:      "How to use React with Redux "
date:       2019-02-05 06:39:39 +0000
permalink:  how_to_use_react_with_redux
---


After finishing my final project on React with Redux, I have changed my opinion on using Redux along with React. Before the project I think Redux can be overwhelming at first. However, shortly after I start working on my final project, I came to appreciate the beauty of Redux, that, in fact, it 's impossible to manage the states and data flow in large React apps without Redux. 

In order to use Redux with React, we need to install a package, `react-redux` in the root directory of our app. If you nested the react client folder inside rails, then install the library in client directory. 

An important method from `react-redux` is `connect()`, a method that registered the React component to the Redux store. 

What is the Redux store?    --- The Redux store stores all the moving parts of Redux.  It's a fundemental part of our app that holds the state of the entire application. To create a store, we can use the `createStore` method from `redux` library. 

That's where all the magic begins! 

The file structure of a React+Redux App would look like this:

```
src/
     actions 
     components
     containers
     reducers 
```
I came accross to a useful [diagram](https://www.youtube.com/watch?v=hiaqhI62zZs) interpreting the associations between the components. 

![](https://i.ytimg.com/vi/hiaqhI62zZs/hqdefault.jpg)

We dispatch an action to tell the store that we need to update the state, then reducer will take the appropriate steps to create the next state according to the action type it receives. Reducer returns the new state to store and store will pass the updated state to React. 





