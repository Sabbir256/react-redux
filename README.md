## Getting started with react-redux

Redux is a nightmare to many. I too had problem understanding redux when I started learning it, cause there was a lot of boilerplate code, did not understood the store properly and everything seemed too complex. But I kept at it until I got the hang of it. I will try to describe it in simple terms here, so that anyone can understand the basic of redux.

I have created a demo project at [CodeSanxbox](https://codesandbox.io/s/redux-toolkit-q0qcyp?file=/src/index.js). It's a [todo](https://codesandbox.io/s/redux-toolkit-q0qcyp?file=/src/index.js) app that uses redux to control its state. You can follow along the project.

### What is Redux?
For those who are new to redux, it is a JavaScript library to control your application states. If you have the basic knowledge of react, you know that an application can have multiple states, but maintaining states seperately becomes hassle when the same state has to be used in multiple components. We can use **React Context**, but there is problem with using it. We know that react renders application when a state changes. But we don't want to render the whole application just because of a simple state change somewhere. In this case, redux comes to the rescue.

What redux does is, it maintains a single source of truth for your application. The states are kept at a store, and you can not modify states directly. You have to dispatch an action to change any state. And reducers are the way to do so. Now, you are confused. What is a store, action and reducers? You should be. Because redux is all about these 3 things. I will try to describe it in simple terms.

### Describe Redux to a 5 year old
The key points to remember about redux are:
- Store
- Reducer
- Action

Let's try to understand it using an example. Our characters name is John.

**[Store]** : John keeps his money in the bank. One day he wanted to take out some of his money from the bank. So, he thought he should go to the bank to do so. He got ready and went to the bank. Banks keep their money in the vault. So think of a redux store as a bank vault. All the application states are kept into it.

**[Reducer]** : Now, after going to the bank, John could get into the vault and take out some money, because it's his money. But that's illegal, and John can not do that. The bank keeps record of how much money is in the vault and how much money is in a persons account. So what John does after going to the bank is, he goes to the managers office and tells him that he needs to take out some money from his account. Here the bank manager can be compared as reducer in redux. States can only be changed using reducers.

**[Action]** : After hearing upon his request, the bank manager asks John for a check and tells one of his employee to take out some money from the vault and update Johns account. This can be compared to an action in redux. Reducers uses action to update states. And actions can be dispatched from anywhere in the application.

### Installation
We will be using @reduxjs/toolkit, which is a standard way for writing redux logic now. To get started create a react application with ```create-react-app```. Now we have to install redux packages. Open a terminal within the project directory and type
```
npm install @reduxjs/toolkit react-redux
```
or if you use yarn then type
```
yarn add @reduxjs/toolkit react-redux
```
### Create a Redux Store
First of all, create a new folder in your ```/src``` directory. Let's name it as redux. Within redux directory create a file named ```/src/redux/store.js```. Paste the code from below within that file.
```jsx
import { configureStore } from '@reduxjs/toolkit';
export default configureStore({
  reducer:{}
});
```
Initially, the reducer object is empty. We can add as many reducers as we want within this object. We will populate it as we go along the project.

### Provide the Redux Store to React 
Once the store has been created, we need to make it available to the components of the application. If you are familiar with React Context, then you know that we need to wrap the App component with context provider to make it available to all components. Same logic is applied here, but we apply it in the top level, in ```/src/index.js```. We import ```<Provider>``` from react-redux and wrap the ``<App/>`` component with it.

```JSX
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import App from "./App";

import store from "./redux/store";
import { Provider } from "react-redux";

const rootElement = document.getElementById("root");
const root = createRoot(rootElement);

root.render(
  <StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </StrictMode>
);

```
