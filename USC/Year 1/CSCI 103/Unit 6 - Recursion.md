## Definition
Defining an object, mathematical functions, or computer function in terms of itself
- Want to express the solution in terms of smaller versions of itself and a base/terminating case.
Anything that can be done recursively can be done in a loop (loops are generally more efficient than loops)

```c++
int fact(int n)
{
	if(n == 1){
		//base case
		return 1;
	}
	else{
		//recursive case
		return n*fact(n-1);
	}
}
```

#### Head vs Tail Recursion
Tail recursion
- Work comes first, then recursion
Head recursion
- Recursion comes first, then work on the way back

## General Principles
Generally recursive functions are responsible for only **1** value/element/item and use recursion to handle all the remaining items.

Determine how to combine the 1 element you are responsible
for and the answer returned by recursion
- Assume via the "magic of recursion" you get the answer for all remaining
elements. How can you combine that with your first element to form the large solution

### Summing an Array
```c++
int rsum_it(int data[], int len){
	if(len == 1){
		return data[0];
	}
	else{
		int sum = rsum_it(data, len-1);
		return sum + data[len-1];
	}
}
```

### Recursive Binary Search
```c++
binSearch(target, list[], start, end) //start is inclusive end is exclusive, e.g. 0-9 for first 9 (0-8)
```
Base case, empty list (if end-mid+1 == 0)
Pick mid item
EQ->Found=>return mid - second base case
LT=>return answer to binSearch(start,mid) integer division
GT=>return answer to binSearch(mid+1,end)

