---
title: "Recursive Problems Benefit from Recursive Solutions · Programming should be enjoyable"
source: "https://jnkr.tech/blog/recursive-benefits-recursive"
author:
published:
created: 2026-03-14
description: "A note on maintainability"
tags:
  - "blog"
---
### A note on maintainability

It seems to be common knowledge that any recursive function can be transformed into an iterative function. This post is an argument as to why you may not want to do that.

### Tree traversal

One factor I consider when evaluating the quality of a solution is the degree to which its approach magnifies perturbations in requirements. As an example, consider a function which converts a binary tree to a linked list. Here’s the data we’ll be dealing with:

```typescript
type LinkedList<T> = {
    tag: "Cons",
    value: T,
    tail: LinkedList<T>
} | {
    tag: "Empty"
}

// Helper functions

function emptyList<T>(): LinkedList<T> {
    return { tag: "Empty" };
}

function concat<T>(head: T, tail: LinkedList<T>): LinkedList<T> {
    return {
        tag: "Cons",
        value: head,
        tail
    }
}
```

The use of linked lists will be somewhat incidental here; I chose them because their construction must be done in a proper order. This makes their construction a good stand-in for more complex requirements which may occur in the real world such as when calling side-effecting functions where order may matter.

Our initial example will be a preorder traversal. This traversal should visit the root node first, then the left subtree, then the right subtree. First, defining our input (using some helper functions):

```typescript
function tree<T>(
    rootContents: T, 
    left: BinaryTree<T> | null, 
    right: BinaryTree<T> | null): BinaryTree<T> {
    
    return {
        contents: rootContents,
        left,
        right
    }
}

function leaf<T>(contents: T): BinaryTree<T> {
    return {
        contents,
        left: null,
        right: null
    }
}

const orderedTree = tree(
    1,
    tree(2, leaf(3), leaf(4)),
    tree(5, leaf(6), leaf(7))
)
```

A preorder traversal of `orderedTree` should push the numbers 1 through 7 onto a list in order, resulting in a list with 7 at its head and 1 at the end of its tail.

Here’s how we can define such a traversal recursively:

```typescript
function flattenTreePreRec<T>(tree: BinaryTree<T>): LinkedList<T> {
    function recursive(tree: BinaryTree<T> | null, acc0: LinkedList<T>): LinkedList<T> {
        if (!tree) return acc0;
        const acc1 = concat(tree.contents, acc0);
        const acc2 = recursive(tree.left, acc1);
        return recursive(tree.right, acc2);
    }

    return recursive(tree, emptyList());
}
```

This function relies on the common functional programming idiom of passing an accumulator through recursive calls. At the top level this accumulator starts out empty, and subsequent calls grow the accumulator with new items.

Now, consider a postorder traversal, which visits the right node, then the left node, then the root node. This traversal runs “backwards” from the previous, and given our example input it should produce a sorted list with 1 at its head and 7 at the tip of its tail. Here’s a recursive implementation:

```typescript
function flattenTreePostRec<T>(tree: BinaryTree<T>): LinkedList<T> {
    function recursive(tree: BinaryTree<T> | null, acc0: LinkedList<T>): LinkedList<T> {
        if (!tree) return acc0;
        const acc1 = recursive(tree.right, acc0);
        const acc2 = recursive(tree.left, acc1);
        return concat(tree.contents, acc2);
    }

    return recursive(tree, emptyList());
}
```

This solution looks extremely similar to the previous one, which is a good thing. Our requirements have experienced a small change (reversing the traversal order) and our solution has responded with a small modification.

Next, let’s consider an iterative approach. This is the “standard” preorder approach which I’ve encountered everywhere I’ve looked for such a thing:

```typescript
function flattenTreePreIter<T>(tree: BinaryTree<T>): LinkedList<T> {
    const stack: Array<BinaryTree<T>> = [tree];
    let flattened = emptyList<T>();

    while (stack.length) {
        const node = stack.pop()!;
        flattened = concat(node.contents, flattened)

        if (node.right) {
            stack.push(node.right);
        }

        if (node.left) {
            stack.push(node.left);
        }
    }

    return flattened;
}
```

In this case we explicitly manage a stack which allows us to track the need to process each node’s children after we process the nodes themselves. I do not believe there is any getting around this; if we can’t store the intermediate states of the computation on the call stack, we have to store them somewhere else.

I think this implementation is significantly harder to read about. When I read the recursive solutions I can see relatively quickly that they are correct. The iterative solution contains distracting concerns, dealing with concepts that aren’t present in the problem statement. This is the definition of incidental complexity, and this complexity makes it significantly harder to understand the order in which nodes will be sequenced.

This is bad for our current challenge. Not only is the iterative solution overwhelmed with noise which obscures the intent of the algorithm, this noise is also tightly coupled to assumptions about the requirements. Once we’ve decided to change the traversal order we’ve invalidated the core of our approach and will need to start from scratch.

While searching for solutions to the iterative postorder problem I repeatedly encountered a “single stack” solution and a “double stack” solution. I will not dig into their implementations, partially because they aren’t relevant to the point I’m trying to make and partially because I can’t figure out how the single stack solution works for the life of me. Here they are:

```typescript
// Based off of https://stackoverflow.com/questions/1294701/post-order-traversal-of-binary-tree-without-recursion
function flattenTreePostIterSingle<T>(tree: BinaryTree<T>): LinkedList<T> {
    const stack: Array<BinaryTree<T>> = [tree];
    let flattened = emptyList<T>();

    let currentNode = tree;

    while (stack.length) {
        const next = stack[stack.length - 1];

        const finishedSubtrees = next.left === currentNode || next.right === currentNode;
        const isLeaf = !next.left && !next.right;

        if (finishedSubtrees || isLeaf) {
            currentNode = stack.pop()!;
            flattened = concat(currentNode.contents, flattened);
        } else {
            if (next.left) stack.push(next.left);
            if (next.right) stack.push(next.right);
        }
    }

    return flattened;
}

// Based off of https://maxnilz.com/docs/001-ds/tree/001-postorder-traversal/
function flattenTreePostIterDouble<T>(tree: BinaryTree<T>): LinkedList<T> {
    const stack1: Array<BinaryTree<T>> = [tree];
    const stack2: Array<BinaryTree<T>> = [];

    while(stack1.length) {
        const currentNode = stack1.pop()!;

        stack2.push(currentNode);
        if (currentNode.right) stack1.push(currentNode.right);
        if (currentNode.left) stack1.push(currentNode.left);
    }

    let result = emptyList<T>();
    while(stack2.length) {
        const currentNode = stack2.pop()!;
        result = concat(currentNode.contents, result)
    }

    return result;
}
```

These solutions look nothing like the preorder solution. If we had an implementation using the preorder traversal and we were asked to change to the postorder traversal we would have to invent a whole new approach from scratch. Our existing code would turn into wasted effort, the temporary results of work which did not move us any closer to our next goal.

This kind of fragility is why I generally prefer recursive algorithms as the solution to problems on recursive data types. While it is true that an iterative implementation can be produced which is equivalent to any recursive implementation, both the motivating logic behind the implementation and the ability to respond to requirement changes are often lost during this transformation.

### In summary

I think my claim could be generalized further: Code becomes more maintainable when its implementation reflects its specification. Changes in specification are more likely to be small than large, and when the code and specification are in tight correspondence this means that the associated code changes are also more likely to be small. When the two have significantly diverged, all bets are off.

---

*All code samples shown in this post are released into the public domain under a CC0 license. Full example code and license text may be found [here](https://github.com/josephjunker/examples/tree/master/recursive-benefits-recursive).*