---
title: "React Fiber vs Reconciliation in ReactJS"
seoTitle: "react fiber, reconciliation react"
seoDescription: "React Fiber vs Reconciliation in ReactJS"
datePublished: Tue Aug 29 2023 21:17:48 GMT+0000 (Coordinated Universal Time)
cuid: cllwt7uv900040akz2ebb9dco
slug: react-fiber-vs-reconciliation-in-reactjs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693344469842/1e9d1716-4759-4baf-87d1-5623e431530b.jpeg
tags: frontend, web-development, webdev, reactjs, frontend-development

---

### Reconciliation

Reconciliation is algorithm which React.js uses to differentiate one tree with another to determine which parts need to be changed. Basically it keeps the track of UI and data layers when there is diff in both layers react uses virtual DOM and updates the changes by re-rendering the specific component.

### React Fiber

React Fiber is used to increase React's suitability for areas like animation, layout, and gestures. Its headline feature is incremental rendering: the ability to split rendering work into chunks and spread it out over multiple frames.  
Basically react fiber is a architecture which splits the work and updates the only component that needs to change.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5fu7s6rledwlhsdqbc0z.jpeg align="left")