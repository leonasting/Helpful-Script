1. torch.size [source](https://pytorch.org/docs/stable/generated/torch.Tensor.size.html)

- Used for retrieving dimensions of torch variable.
```
>>> t = torch.empty(3, 4, 5)
>>> t.size()
torch.Size([3, 4, 5])
>>> t.size(dim=1)
4
```

2.Save on GPU, Load on CPU
```
# Specify a path to save to
PATH = "model.pt"

# Save
torch.save(net.state_dict(), PATH)

# Load
device = torch.device('cpu')
model = Net()
model.load_state_dict(torch.load(PATH, map_location=device))
```
