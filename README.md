# curring
Task of curring

Currying in JavaScript is a technique in functional programming where a function, instead of taking all its arguments at once, takes them one at a time. In other words, a curried function returns a new function that expects the next argument until all arguments are provided.
Consider a simple function that adds three numbers:
function add(a, b, c) {
    return a + b + c;
}
Normally, you would call this function as add(1, 2, 3), and it would return 6.

However, if we transform this function into a curried version, it would look like this:
function curriedAdd(a) {
    return function(b) {
        return function(c) {
            return a + b + c;
        };
    };
}
Now, instead of passing all arguments at once, you call the function like this:
curriedAdd(1)(2)(3); // Returns 6
Explanation:
The curriedAdd function takes the first argument (a) and returns a new function that takes the next argument (b).
The second function then returns another function that takes the final argument (c).
When all arguments are provided, the original function logic is executed.