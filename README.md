
# A pytorch implementaiton of [GAN "Steerability" without optimization](https://arxiv.org/pdf/2012.05328.pdf) 


![logo](teaser.jpg)

## GENERAL

Generally, our methods are coded in the file BigGAN.py. Each path can be extracted by directing the "method" flag accordingly. Full description can be found below.
Also, for easier reproducing, you can use main.py.

## USER-SPECIFIED GEOMETRIC TRANSFORMATIONS

![Closed form solution ](https://github.com/nsping13/GAN-Steerability-without-optimization/blob/main/User%20Specified.jpg)

Path | Flag
------------ | -------------
Linear  | 'l_shifty', 'l_zoom' and 'l_shiftx'
Newmann  |  'nl_shifty', 'nl_zoom' and 'nl_shiftx'
Great circle | 'gcircle_shifty', 'gcircle_zoom' and 'gcircle_shiftx'


## UNSUPERVISED EXPLORATION OF TRANSFORMATIONS
The principal latent space directios are based on the right singular vectors of the SVD of the FC weight matrix.  
Here the flags for the first layer unsupervised paths i.e., all principal latent space directions extracted from the first weight matrix:

Path | Flag
------------ | -------------
Linear  | 'svd_linear'
Great circle | 'svd_gcircle'
Small circle | 'svd_scircle'

And here the corresponding paths of other scales:

Path | Flag
------------ | -------------
Linear  | 'linearin'
Great circle | 'greatin'
Small circle | 'smallin'

The specific order direction is set by the index parameter. 

## PLUG AND PLAY  

For convenience we also uploaded separate modules for directions and walks. Please see modules.py. 
You are invited to take the module you need and just plant in your code environment. This allows using separately methods for extracting directions and methods for constructing walks from given directions.

## BigGAN model 
We downloaded the G_ema.pth for the BigGAN model from [here](https://drive.google.com/drive/u/0/folders/1ak7yc1xcDK6lmPH7-DvJ4-rHYmAeqhSw?ths=true), however you can also use the TFhub and the pytorch implementation. Please see [here](https://github.com/ajbrock/BigGAN-PyTorch). 
You are also invited to explore Imagenet classes [here](https://gist.github.com/yrevar/942d3a0ac09ec9e5eb3a)

## Cite
If you are using this code and, please cite us:

@article{spingarn2020gan,

title={GAN Steerability without optimization},

author={Spingarn-Eliezer, Nurit and Banner, Ron and Michaeli, Tomer},

journal={arXiv preprint arXiv:2012.05328},

year={2020}

}

For any question or issue, write to me!
nurit.spini@gmail.com


