1. torch.size [source](https://pytorch.org/docs/stable/generated/torch.Tensor.size.html)

- Used for retrieving dimensions of torch variable.
```
>>> t = torch.empty(3, 4, 5)
>>> t.size()
torch.Size([3, 4, 5])
>>> t.size(dim=1)
4
```
