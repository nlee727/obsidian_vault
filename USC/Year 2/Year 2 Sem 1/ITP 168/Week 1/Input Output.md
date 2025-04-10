```MATLAB
>> name = 'Nathan';
>> disp(['Hi ', name])
Hi Nathan
```

Input function will simply replace the input function with the variable. Quotes are needed when entering strings

```MATLAB
clc
name = input("Name? ");
disp(['Hi ', name]);

//////

Name? 'Nathan'
Hi Nathan
>> 
```

```MATLAB
clc

name = input('Name? ','s');

age = input('Age? ');

gpa = input('GPA? ');

disp(['Hi ', name, ' you are ', num2str(age), ' years old and your gpa 
is ', num2str(gpa)]);
```

#### fprintf()
```MATLAB
clc

name = input('Name? ','s');

age = input('Age? ');

gpa = input('GPA? ');

fprintf('Hi %s. You are %d years old and your gpa is %4.2f\n', name, age, gpa)
```

- in 4.2, the 4 represents the dedicated size of the digit, while the .2 represents digits after the decimal
