## Getting started with react-redux

Redux is a nightmare to many. I too had problem understanding redux when I started learning it, cause there was a lot of boilerplate code, did not understood the store properly and everything seemed too complex. But I kept at it until I got the hang of it. I will try to describe it in simple terms here, so that anyone can understand the basic of redux.

I have created a demo project at [CodeSanxbox](https://codesandbox.io/s/redux-toolkit-q0qcyp?file=/src/index.js). It's a [todo](https://codesandbox.io/s/redux-toolkit-q0qcyp?file=/src/index.js) app that uses redux to control its state. You can follow along the project.

### What is redux?
For those who are new to redux, it is a JavaScript library to control your application state. If you have the basic knowledge of react, you know that an application can have multiple states, but maintaining states seperately becomes hassle when the same state has to be used in multiple components. We can use **React Context**, but there is problem with using it. We know that react renders application when a state changes. But we don't want to render the whole application just because of a simple state change somewhere. In this case, redux comes to the rescue.

What redux does is, it maintains a single source of truth for your application. The states are kept at a store, and you can not modify states directly. You have to dispatch an action to change any state. And reducers are the way to do so. Now, you are confused. What is a store, action and reducers? You should be. Because redux is all about these 3 things. I will try to describe it in simple terms.

### Describe redux to a 5 year old
The main 
