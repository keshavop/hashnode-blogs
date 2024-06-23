---
title: "Redux vs Context API: When to use them"
seoTitle: "Redux vs Context API: When to use them"
seoDescription: "Redux vs Context API: When to use them"
datePublished: Sun Jun 23 2024 20:11:04 GMT+0000 (Coordinated Universal Time)
cuid: clxrzhr4k000108lgeoufdove
slug: redux-vs-context-api-when-to-use-them
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719173334393/82a4e0cd-f543-4420-9380-603a6b419212.avif
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1719173440723/2500f0d2-c442-4b68-842d-4c8902b709f7.avif
tags: javascript, reactjs, redux

---

The simplest way to *pass data from a parent to a child* in a **React Application** is by passing it on to the child's `props`. But an issue arises when a *deeply nested child requires data from a component higher up in the tree*. If we pass on the data through the `props`, *every single one of the children would be required to accept the data and pass it on to its child*, leading to **prop drilling**, a terrible practice in the world of React.

To solve the **prop drilling** issue, we have **State Management Solutions** like **Context API** and **Redux.** *But which one of them is best suited for your application?* Today we are going to answer this age-old question!

# What is the Context API?

Let's check the official documentation:

> In a typical React application, data is passed top-down (parent to child) via props, but such usage can be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree.

**Context API** is a built-in **React** tool that does not influence the final bundle size, and is integrated by design.

To use the **Context API**, you have to:

1. Create the **Context**
    
    ```sql
    const Context = createContext(MockData);
    ```
    
2. Create a **Provider** for the **Context**
    
    ```sql
    const Parent = () => {
        return (
            <Context.Provider value={initialValue}>
                <Children/>
            </Context.Provider>
        )
    }
    ```
    
3. Consume the data in the **Context**
    
    ```sql
    const Child = () => {
        const contextData = useContext(Context);
        // use the data
        // ...
    }
    ```
    

# So What is Redux?

Of course, let's head over to the documentation:

> Redux is a predictable state container for JavaScript apps.
> 
> It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. On top of that, it provides a great developer experience, such as live code editing combined with a time-traveling debugger.
> 
> You can use Redux together with React, or with any other view library. It is tiny (2kB, including dependencies), but has a large ecosystem of addons available.

**Redux** is an **Open Source Library** which provides a *central store*, and *actions to modify the store*. It can be used with any project using **JavaScript** or **TypeScript**, but since we are comparing it to **Context API**, so we will stick to **React-based Applications**.

To use **Redux** you need to:

1. Create a **Reducer**
    
    ```sql
    import { createSlice } from "@reduxjs/toolkit";
    
    export const slice = createSlice({
        name: "slice-name",
        initialState: {
            // ...
        },
        reducers: {
            func01: (state) => {
                // ...
            },
        }
    });
    
    export const { func01 } = slice.actions;
    export default slice.reducer;
    ```
    
2. Configure the **Store**
    
    ```sql
    import { configureStore } from "@reduxjs/toolkit";
    import reducer from "./reducer";
    
    export default configureStore({
        reducer: {
            reducer: reducer
        }
    });
    ```
    
3. Make the **Store** available for data consumption
    
    ```sql
    import React from 'react';
    import ReactDOM from 'react-dom';
    import { Provider } from 'react-redux';
    import App from './App.jsx'
    import store from './store';
    
    ReactDOM.render(
        <Provider store={store}>
            <App />
        </Provider>,
        document.getElementById("root")
    );
    ```
    
4. Use **State** or **Dispatch Actions**
    
    ```sql
    import { useSelector, useDispatch } from 'react-redux';
    import { func01 } from './redux/reducer';
    
    const Component = () => {
        const reducerState = useSelector((state) => state.reducer);
        const dispatch = useDispatch();
        const doSomething = () = > dispatch(func01)  
        return (
            <>
                {/* ... */}
            </>
        );
    }
    export default Component;
    ```
    

That's all *Phew!* As you can see, **Redux** requires way more work to get it set up.

# Comparing Redux & Context API

| Context API | Redux |
| --- | --- |
| Built-in tool that ships with React | Additional installation Required, driving up the final bundle size |
| Requires minimal Setup | Requires extensive setup to integrate it with a React Application |
| Specifically designed for static data, that is not often refreshed or updated | Works like a charm with both static and dynamic data |
| Adding new contexts requires creation from scratch | Easily extendible due to the ease of adding new data/actions after the initial setup |
| Debugging can be hard in highly nested React Component Structure even with Dev Tool | Incredibly powerful Redux Dev Tools to ease debugging |
| UI logic and State Management Logic are in the same component | Better code organization with separate UI logic and State Management Logic |

From the table, you must be able to comprehend where the popular opinion ***Redux*** *is for large projects &* ***Context API*** *for small ones* come from.

Both are excellent tools for their own specific niche, **Redux** is overkill just to pass data from parent to child & **Context API** truly shines in this case. When you have a lot of dynamic data **Redux** got your back!

So you no longer have to that guy who goes:

[![meme](https://res.cloudinary.com/practicaldev/image/fetch/s--ARPMjK37--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/smhdsuy15m79b3r6v3yf.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--ARPMjK37--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/smhdsuy15m79b3r6v3yf.png)

# Wrapping Up

In this article, we went through what is **Redux** and **Context API** and their differences. We learned, **Context API** is a *light-weight solution* which is more suited for *passing data from a parent to a deeply nested child* and **Redux** is a more *robust* ***State Management*** *solution*.

**Happy Developing!**

# Thanks for reading