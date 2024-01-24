---
title: Kaggle
author: Agastya Patel
date: 2024-01-20
date-modified: today
categories: ['Kaggle', 'Hugging Face']
---

## Access kaggle on your machine

### Setting up kaggle in CLI
1. `pip install kaggle`
2. Setup the JSON: User have to set their email and key in this json file.
   Linux: ~/.kaggle/kaggle.json
   Windows:  C:\Users\<Windows-username>\.kaggle\kaggle.json

### Create New Notebook in Local
Initialize : `kaggle kernels init -p /path/to/folder`
In your nb folder  a metadata file will be generated
Set title and id; prefer to keep them same and just strip `spaces, caps and symbols` in id; Add your nb name and any dataset used.

> More on metadata key values: https://github.com/Kaggle/kaggle-api/wiki/Kernel-Metadata

Push Command `kaggle kernels push -p /path/to/folder` (remove path flag if in cwd is dir with nb)

### Accessing Dataset

```py
kaggle datasets list -s [KEYWORD]      //Search
kaggle datasets download -d [DATASET]  //download
```
### Creating dataset
Initialize: `kaggle datasets init -p /path/to/dataset`
Add metadata in `datapackage.json`
Push: `kaggle datasets create -p /path/to/dataset`
