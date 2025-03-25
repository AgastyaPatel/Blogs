---
title: "FastAI Setup [2025]"
author: "Agastya Patel"
categories: [Notes, FastAI, Tools]
---
In this section we'll be going through the setting up the wsl for FastAI.

This guide will help you out with setting up the fastai on your mac quickly.

*Prerequistes*:
   -  Conda Command Line Tool


1. Create conda environment
```
conda create -n fastai-311 python=3.11
```
2. Install pytorch
> Recently pytorch dropped support for distribution over conda channels so pip3 is the only way to get it done
```
pip3 install torch torchvision torchaudio
```
3. Install ipython and jupyterlab
```
conda install ipython jupyterlab
```
4. Install fastai & fastbook
> fastchan has been deprecated. Use fastai as the channel to download the package from.
```
conda install -c fastai 
```
5. Install sentencepiece (tokenizer by google)
```
conda install sentencepiece
```
