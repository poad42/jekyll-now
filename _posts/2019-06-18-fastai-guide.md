---
layout: post
title: A simple guide to install fastai on your local machine
---

Note: This guide assumes you have a NVIDIA GPU installed on your PC. Also I am running Manjaro Linux and running the latest Nvidia Drivers.(The following steps should works on any distro but make sure you installed nvidia's newest proprietary drivers to avoid cuda realted errors) 


The Guides online are riddled with excessive steps or break everything entirely. So decided write on my own :p

##Steps

1) Download [Anaconda](https://www.anaconda.com/distribution/#download-section) 
```
bash "path to anaconda script".sh
source ~/.bashrc
conda config --set auto_activate_base false
```


2)Create a dedicated environment for fastai do this by running
```
conda create -n fastai
conda activate fastai
```

3)Setup some conda stuff in the new env (don't know why it doesn't do them automatically, maybe someone can tell me why?)
```
conda install conda
conda install anaconda
conda install python
```
4)Install pip
```
conda install pip
```

5)Install fastai from pip

```
pip install fastai
```
And success!


![_config.yml]({{ site.baseurl }}/images/fastai.png)

##Warnings and Mistakes I made
```
conda install -c fastai fastai
```
Using conda to install fastai and pytorch always resulted in me getting the error "no module fastai" in the notebook, when I try to import the module. Hence I used pip to install fastai, which automatically installs pytorch and cudatoolkit.
