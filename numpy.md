1. To generate random sample from given list.

[source](https://numpy.org/doc/stable/reference/random/generated/numpy.random.choice.html)<br>
Note Params: Input list/ value like 5 will be considered as np.arrange(5)<br>
replace= False -> Unique no repeatition.<br>
p= list of probabilities.

```
np.random.choice([1,2,3,4,5], 3, replace=False, p=[0.1, 0, 0.3, 0.6, 0])
```

2. Elementwise modular division 
[source](https://numpy.org/doc/stable/reference/generated/numpy.mod.html)<br>
```
Example of 0-9 values in sequence which can start from 4 
sentence = np.mod(np.arange(4,14), 10)
array([4, 5, 6, 7, 8, 9, 0, 1, 2, 3], dtype=int32)
```
