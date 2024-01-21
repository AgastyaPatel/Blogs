---
title: PyTorch Reference
author: Agastya Patel
date: 2024-01-16
date-modified: today
categories: ['Reference']
---
### Getting started
Creating tensor: `tns = torch.tensor(2500, dtype = torch.int)` ## torch.float is another dtype
BaseClass for all neural networks : `nn.Module`
`nn.Linear` and `nn.Sequential` are objects/derived class of `nn.Module` class/Parent Class. 

```py
nn.Linear(2,3)  // Initializes with random paramters

# Building sequential network
model = nn.Sequential(  
    nn.Linear(2,3),  
    nn.ReLU(),  
    nn.Linear(3,1))
model(input)   //FeedForward

# buildinv custom network
class NN_Regression(nn.Module):
	super(NN_regression, self).__init():
	#initialize components
		self.layer1 = nn.Linear(3,6)
		self.layer2 = nn.Linear(4,1)
		self.relu = nn.ReLU()
	def forward(self, x):
		x = self.layer1(x)
		x = self.relu(x)
		x = self.layer2(x)
		return x
		
optimizer = optim.Adam(model.parameters(), lr=0.01)
loss = nn.MSELoss()

MSE = loss(model(input), y)
MSE.backward()   #Backward propogation or gradient calculation
optimizer.step() #Stepping
optimizer.zero_grad()  #reset the gradients

# Model Evaluation
model.eval()
with torch.no_grad():
	test_MSE = loss(model(X_test), y_test)
torch.save(model, 'model.pth')
torch.load('model.pth')
```

To split dataset into validation and testing; use sklearn.model_selection.train_test_split

## PyTorch references and functions

#### Non Linear Functions
| Name | Functions | Notes |
| ---- | ---- | ---- |
| ReLU | `nn.ReLU()` | | 
| Sigmoid | `nn.Sigmoid()` | | 

#### Loss Functions
| Name | Functions | Notes |
| ---- | ---- | ---- |
| Absolute Mean Error or L1 norm | `torch.nn.functional.l1_loss(a,b)` |  |
| Root Mean Square Error or L2 norm | `torch.nn.functional.mse_loss(a,b)` |  |

#### Optimizers
| Name | Functions | Notes |
| ---- | ---- | ---- |
| SGD | `torch.optim.SGD(model_paramets, lr)`| |
| Adam | `torch.optim.ADAM(model_paramets, lr)`| |

#### Linear Regressions
| Name | Functions | Notes |
| ---- | ---- | ---- |
| Linear Regression | `nn.Linear(n_weights/n_inputs, n_bias/n_outputs)` | `wx + b` |
