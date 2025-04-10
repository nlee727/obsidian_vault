array(index)

Indexing of arrays starts at 1


x(\[index1 index2])
create an array with index1 and index 2

Since 1:2:9 creates an array type, you can x(1:2:9) to index odd numbers up to 9

Colon notation is very useful when there is a pattern

For example, retrieving the first column would be
```MATLAB
x(1:end, 1)

same as

x(:,1)
```
