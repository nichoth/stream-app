# trying things with streams

Let's make applications in javascript 

-----------------------------------

## what are we doing?

What are some things that we want? 

We want to know what's going on in the application

We want to know when we write code that is bad

We want to be able to change the app quickly without breaking it


----------------------------------------------


What if all our application code was static and synchronous?


---------------------------------------


Our application has many *domain models* -- state machines that reflect persisted state and are re-used in many views in the app. These are distinct from view state, which is ephemeral and specific to the UI.

We want tests that tell us if anything breaks. If someone changes an event that is emitted by a view, does that break the application? What about if someone changes a model's state and breaks the view, will our tests catch that?


## some terminology

A stream contains application events or other streams. 

Events are objects with a key and a value.

Effects are a map from events to streams. They get called with the current state of the store. If an effect does something synchronous it returns an event, if does something async it returns a stream.

A view is a duplex stream that renders to the DOM when it is written to, and emits events from dom interactions.


---------------------------------


Our state is a tree. Nodes become less generic as they get closer to the root of the tree. 

```
    a
  /   \
 b     c
```

Here `a` would be the view state specific to our app. `b` and `c` might be domain models -- state that is re-used across the app.



## todo

* typescript + pull-stream



