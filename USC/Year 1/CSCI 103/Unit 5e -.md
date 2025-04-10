Getting order right
Check whether the input fails' before you use the result

#### Getting All the inputs
istream class defines an operator bool which returns true if stream didnt fail
```c++
while(cin >> val){
	sum+=val;
}
```
while you try to get data and do not fail

By default, getline for string class has '\\n' as its delimiter, you can specify with the third argument getline(istream &is, string &str, char delim='\\n'

### C++ String stream 
Applications:
can parse a string of many values into separate variables

