---
title: PyTorch Reference
author: Agastya Patel
date: 2024-01-16
date-modified: 2024-01-16
categories: ['Reference']
---
Pytorch refernces and functions
```python
#Creating tensor
rent_tensor = torch.tensor(2500, dtype = torch.int) ## torch.float is another dtype

```

|  | Name | Functions | Mathematical Expression |
| ---- | ---- | ---- | ---- |
| Loss  Function | Absolute Mean Error or L1 norm | `torch.nn.functional.l1_loss(a,b)` |  |
| Loss  Function | Root Mean Square Error or L2 norm | `torch.nn.functional.mse_loss(a,b)` |  |
|  | Loop over tensor while making comparision | `torch.where(targets==1, 1-predictions, predictions)` |  |
| Normaliser | Sigmoid | `torch.sigmoid` | ``1/(1+torch.exp(-x))`` |
| Linear Regression |  | `nn.Linear(n_weights, bias)` | `wx + b` |
|  |  |  |  |
