```MATLAB
>> A = [6 2 -3; 2 -5 1; -1 -2 -7]

A =

     6     2    -3
     2    -5     1
    -1    -2    -7

>> b = 1;4;5

ans =

     5

>> b = 1;4;5

ans =

     5

>> b = [1;4;5]

b =

     1
     4
     5

>> inv(A)*b

ans =

    0.1891
   -0.8255
   -0.5055

>> 
```
Shorthand
```MATLAB
x = A\b
```

#### Element Wise Operation
```MATLAB
>> x = [2 4 6]
>> x.^2

ans =

     4    16    36
```
- Without the dot, you would be performing a matrix multiplication 1x3 by 1x3

### Numerical Simulation
```MATLAB
p = 0:10

denom = 2.^p

f = 1./denom

sum(f)
```
