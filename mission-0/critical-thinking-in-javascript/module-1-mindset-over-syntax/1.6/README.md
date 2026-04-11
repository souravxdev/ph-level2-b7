# Visual comparison of different time complexity

- We always plan about the worst case of an algorithm.
- O(n) - Single for loop, arr.map(), arr.forEach(), arr.find()
- n - number of element

```
for (...){ // n times
    ....
}
```

- O(n^2) - Nested for loop

```
for (...){ // n times
    for (...){ // n times
        ....
    }
}
```

- O(1) - Constant

```
Find an element in an array:
arr = [1,2,3,4,5]
arr[2] = 3

Find any property from an object:
obj = {
    name:
    age:
    salary:
}
obj.name = "
```

- Sibling for loop
- n + m - O(n) - if n > m
- n + m - O(m) - if m > n
- n + n = 2n - O(n) - if n = m
- Any cnostant value in time complexity will be ignored

```
for(...){ // n times
    ...
}
for(...){ // m times
    ...
}
```

```
for(let i = 0; i < 5; i++){ // O(1)
    arr[i] = [1,2,3,4,5, .... ,1000000]
}

```
