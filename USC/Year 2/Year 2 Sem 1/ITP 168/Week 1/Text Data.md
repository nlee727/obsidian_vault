Single quotes will return a char array
```MATLAB
name1 = 'nathan';
lname1 = 'lee';
>> a1 = [name1 lname1]

a1 =

    'nathanlee'

```
Double quotes will return a string
```MATLAB
>> a2 = [name2 lname2]

a2 = 

  1×2 string array

    "nathan"    "lee"
```



```MATLAB
>> a4 = ['one' 'two'; 'three' 'four']
Error using vertcat
Dimensions of arrays being concatenated are not consistent.
 
>> a4 = ['one' 'twoZZZ'; 'three' 'four']

a4 =

  2×9 char array

    'onetwoZZZ'
    'threefour'
```