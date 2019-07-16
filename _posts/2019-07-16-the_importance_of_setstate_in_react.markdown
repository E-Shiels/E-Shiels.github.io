---
layout: post
title:      "The Importance of setState() in React"
date:       2019-07-16 16:34:19 -0400
permalink:  the_importance_of_setstate_in_react
---


I recently completed my React/Redux portfolio project assessment, and during that assessment, I was asked about the importance of setState(). I wasn't sure why setState() is so important, and so I am writing this piece to explain it.

React components have internal state, which is a property of the component object. It is an object, and like any other object, it can be changed without using any functions. So why should you use setState()?

There is one major and two less important reasons why you shouldn't mutate state directly.

The biggest reason that you shouldn't mutate state directly is that it will not re-render a component. Changing a name in the state directly using `this.state.name = "Julia"` will not re-render a component, and therefore, you won't see the change. If you used setState (`this.setState({ name: "Julia" })`) will notify React that a change was made and it should re-render.

A less significant reason not to modify state directly is that it may affect performance. setState() is asynchronous and will batch state updates to improve performance. Frequent direct modifications of state may slow down an application.

Another less important reason is that direct state modification also means that you won't be able to take advantage of setState()s reconciliation. setState() uses shallow merges, which reduces the odds of you accidentally overwriting parts of the state you didn't want to be changed.

I hope that this explains why setState() should always be used instead of directly modifying the state object.




### Sources
https://reactjs.org/docs/react-component.html

https://reactjs.org/docs/state-and-lifecycle.html

https://css-tricks.com/understanding-react-setstate/

https://medium.com/pro-react/a-brief-talk-about-immutability-and-react-s-helpers-70919ab8ae7c#.24f7t0qpz

https://daveceddia.com/why-not-modify-react-state-directly/

https://itnext.io/react-setstate-usage-and-gotchas-ac10b4e03d60

https://www.freecodecamp.org/news/understanding-setstate-in-react-ea8982168b49/


