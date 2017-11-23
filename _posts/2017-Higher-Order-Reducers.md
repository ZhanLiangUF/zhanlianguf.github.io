---
layout: post
excerpt: Higher Order Reducers
permalink: /Higher-Order-Reducers
published: true
---

This post is mainly about higher order reducers - which are basically a function that takes in a action and state and returns a new state. Here is a link if you're unfamiliar with reducers - https://redux.js.org/docs/basics/Reducers.html

When using the redux pattern for an enterprise application whether its for UI state(is there a dialog open?) or Cache(think Apollo client), it is important to abstract reducers because as you go you will notice that the structure is very similiar. The following example below is an example of a reducer that can be used to do optimistic updates.

Now you're probably wondering, what exactly is a higher order reducer? It's just a function that takes in some sort of metadata and returns a function that takes in an action and state that returns the new state/cache.

This is just a very contrived example that might be used to update a list on a mutation.

```typescript
function generateReducer<T>(
  newObj: T
): (data: T, prev: Record<string, any>) => any {

    return (data: T, prev: Record<string, any> => {
      const items = prev;
      const itemIndex = items.findIndex(item => item.id === data.id);
      const newItem = {
        ...items[itemIndex],
        ...data,
      }
      items[itemIndex] = newItem;
      return items
    }

}

```

This can even be further refined with a middle layer function that can generate different type of reducers based on a certain condition.
