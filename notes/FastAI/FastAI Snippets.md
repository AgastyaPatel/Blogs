---
title: "FastAI Snippets 01"
author: "Agastya Patel"
date: "2023-12-31"
date-modified: "2023-12-31"
categories: [Notes, FastAI, Utils]
---

Page contains some of the common and usefull snippets.
Pathlib, parallel processing.

## Path
```py
from pathlib import path
path = Path() #Current Dir
#path = Path('Content') #Relative Dir
#path = Path('NB/content') #Absolute Dir
```

# Parallel Process

Bellow `%time` is used to get the time which was required to execute the cell (Here opening up of all image files
`%time sizes = [PILImage.create(O).size for o in files]`

*Using fastcore.parallel module*
This module provides functionality for parallel processing.
Same command above of loading images happens significantly quicker on parallel processing.
```py 
from fastcore.parallel import *
def f(O): return PILImage.create(O).size
```

```py
# This cell is executed quicker because of four threads assigned to the task
%time sizes = parallel(f, files, n_workers = 4)
```

## Add recent models
```py
!pip install timm
import timm
timm.list_models('convnext*') # Prints available model
```
## Fine_Tune:
Fine Tune Freezes the weights of all layers except the last layers.
Calls fit on the last layer
Decreases the learning rate
Unfreezes the model
Fit for number of epoch specified

> half precision floating points (less precise but fast) supported on latest gpus
> .to_fp16() (method for learnerer)

> [!info] Learning rate and lr_find() : Is used to find good learning rate

`!pip list | grep "^fast`