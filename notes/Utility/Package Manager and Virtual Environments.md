---
title: "Package Manager and Environments"
author: "Agastya Patel"
date: "2024-01-24"
date-modified: "2023-12-30"
---
>[!info]- Common used python packages\
>- numPy for working with custom data types\
>- [pandas](https://pandas.pydata.org/) for working with DataFrames.\
>- [scikit-learn](https://scikit-learn.org/stable/) for machine learning.\ 
>- [Matplotlib](https://matplotlib.org/) for visualizations.\
>- [seaborn](https://seaborn.pydata.org/) for statistical visualizations.\
>- [NLTK](https://www.nltk.org/) for text analysis.\
>- [spaCy](https://spacy.io/) for more text analysis.\

There are several virtual environments handler. Here's a nice thread giving brief about those manageres 
https://stackoverflow.com/questions/41573587/what-is-the-difference-between-venv-pyvenv-pyenv-virtualenv-virtualenvwrappe
# venv
I like to use the shipped manager *venv* because it's simple to manage and doesn't require install it additionally

```bash
python -m venv envName
cd envName/scripts 
activate.bat //Activates the virtual enviroment in cmd
source activate //Activates in bash
deactivate //deactivates in bash
where python //returns the path for python interpretor 
get-command -all python //Same as above but used in powershell
pip freeze >> requirements.txt// returns the dependencies of the workspace and save them to requirements.txt file
pip install -r requirements.txt
```

## Q. What is conda, mamba, mambaforge, miniforge?
Conda is a package and environment manager similar to pip for python.
Mamba is C++ based implementation of conda offering faster package installation
MambaForge is mamba based distribution which contains a preset collection of set packages for quicker setup and ready to go operation feasibility.
Miniforge is conda based distribution

> pip does not manage the installation of any code other than python. 
> Eg: PyTorch relies on CUDA so, PIP isn't the preferable way of installing it instead use `conda/mamba`
> Any python library can be installed using PIP

### conda - Annaconda
https://www.dataquest.io/blog/python-vs-anaconda/

```bash
conda --version
conda install jupyter
jupyter notebook
```
