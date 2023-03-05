1. To generate random sample from given list.

[source](https://numpy.org/doc/stable/reference/random/generated/numpy.random.choice.html)
Note Params: Input list/ value like 5 will be considered as np.arrange(5)
replace= False -> Unique no repeatition.
p= list of probabilities.

```
np.random.choice([1,2,3,4,5], 3, replace=False, p=[0.1, 0, 0.3, 0.6, 0])
```
