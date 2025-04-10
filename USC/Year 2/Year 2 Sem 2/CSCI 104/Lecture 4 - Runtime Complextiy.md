## 170 Review
- T(n) is said to be $O(f(n))$ if it is an upper bound
$$
T(n) < a*f(n) \text{ for } n>n_{0}
$$
- T(n) is said to be $\Omega(f(n))$ if it is a lower bound
$$
T(n) > a*f(n) \text{ for } n>n_{0}
$$
- T(n) is said to be $\Theta(f(n))$ if it is both $O(f(n))$ and $\Omega(f(n))$

##### Data Dependent or Not
- Example 1: Finding the size of a linked list does not depend on data, it is just a function of n
- Example 2: Finding if an element exists in the linked lists does depend of the data
##### Worst Case and Big $\Omega$
- If code is not data-dependent, analysis is valid for any input and is already $\Theta$
- O and $\Omega$ are only necessary when runtime is data dependent
- Big $\Omega$ is not best case

- Big O for worst case means regardless of possible inputs the runtime is at most $O(f(n))$
- Big $\Omega$ for worst case is attempting to establish a lower bound for the worse case
    - Start with worse-case and try to find an input case that requires at **least** $f(n)$ steps.
#### Common Summations

Arithmetic Series
$$
\sum_{i=1}^n \frac{n(n+1)}{2} = \theta(n^2)
$$
General Arithmetic Series
$$
\sum _{i=1}^n \theta(i^p) = \theta(n^{p+1})
$$
Geometric Series
$$
\sum_{i=0}^n c^i = \frac{{{c^{n+1}}-1}}{c-1} = \theta(c^n)
$$
Harmonic Series
$$
\sum_{i=1}^n \frac{1}{i} = \theta(\log n)
$$

##### Example 1
```c++
for(int i - 0; i < n; i++){
    if(a[i] == 0){
        for(int j = 0; j < 1; j++){
            a[i] = i*j;
        }
    }
}
```
$$
\sum_{i=0}^{n-1}\left( \theta(1)+O\left( \sum_{j=0}^{i-1} \theta(1) \right) \right)
$$
$$
\sum_{i=0}^{n-1}\theta(1)+\sum_{i=0}^{n-1}\theta(i)
$$
$$
\theta(n)+\theta\left( \frac{{n(n-1)}}{2} \right) =\theta(n)+ \theta(n^2) = \theta(n^2)
$$

##### Example 2
```c++
for(int i = 0; i < n: i++){
    if(i == 0){
        for(int j = 0; j < n; j++){
        a[i][j] = i*j;
        }
    }
}
```
$$
\sum_{i=0}^{n-1}\left( \Theta(1)+O\left( \sum_{j=0}^{n-1}\Theta(1) \right) \right)
$$
$$
\sum_{i=0}^{n-1}\Theta(1)+\sum_{i}\sum_{j=o}^{n-1}\Theta (1)
$$
$$
\Theta(n)+1*\sum_{j=0}^{n-1}\Theta(1) = \Theta(n)+1*\Theta(n)=\Theta(n)
$$
##### Example 3
```c++
for(int i = 1; i <= n; i++){
    int m = sqrt(n);
    if( i % m == 0){
        for(int j = 0; j < n: j++){
            cout << j << " ";
        }
    cout << endl;
    }
}
```
$$
\sum _{i=1}^n
(\Theta(1) +O\left( \sum_{j=0}^{n-1}\Theta(1) \right)
$$
$$
\sum_{i=1}^n \Theta(1)+\sum_{i}\sum_{j=0}^{n-1}\Theta(1)
$$
- If n = 9, inner loop runs 3x, if n=15, loop runs 4x, so $\sqrt{ n }$ times.
$$
\sum_{i=1}^n \Theta(1)+\sum_{k=1}^{\sqrt{ n }}\sum_{j=0}^{n-1}\Theta(1)
$$
$$
\sum_{i=1}^n \Theta(1)+\sum_{k=1}^{\sqrt{ n }}\Theta(n)
$$
$$
\Theta(n)+\Theta(n*\sqrt{ n }) = \Theta(n^{3/2})
$$
##### Example 4
```c++
for(int i = 1; i <= n; i++){
    for(int j = 0; j < n; j += i){
        a[i][j] = i*j;
    }
}
```

##### Example 5
```c++
cont int n = //number;

int main(){
    for(int i = 0; i < n; i++){
        int y = 0;
        for(int x = n; x != 1; x = x/2){
            y++;
        }
    cout << y << endl;
    }
    return 0;
}
```
$$
\sum_{i=0}^{n-1}\left( \Theta(1)+\sum_{j}\Theta(1) \right)
$$
$$
\sum_{i=0}^{n-1}\Theta(1)+\sum_{i=1}^n
\sum_{j}\Theta(1)$$
$$
\Theta(n)+\sum_{i=1}^n
\sum_{j}\Theta(1)
$$