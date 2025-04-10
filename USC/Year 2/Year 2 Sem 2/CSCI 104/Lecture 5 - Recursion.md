Solution can be expressed in terms of itself and a base case

##### Tail Recursion
Producing the sum as you walk down the list then returning the final answer back up the list

### Analyzing Runtime of Recursion
- Setup and solve a recurrence relationship for the runtime
$$
T(n)=1+T(n-1), T(0)=1
$$
$$
=1+1+T(n-2)
$$
$$
n+1 = \Theta(n)
$$
### Recursion Do's and Don'ts
- Check for head == NULL rather than head->next when possible
    - You don't want to dereference the NULL pointer
- Each function should only access/modify the data of one node/item
- If you need multiple return values you can use reference parameters

