
# An official pytorch implementaiton of [GAN "Steerability" without optimization](https://arxiv.org/pdf/2012.05328.pdf) 


![logo](teaser.jpg)


Generally, our methods are coded in the file BigGAN.py. Each path can be extracted by directing the "method" flag accordingly.
For easier reproducing, you can use main.py.

## USER-SPECIFIED GEOMETRIC TRANSFORMATIONS

![Closed form solution ](https://github.com/nsping13/GAN-Steerability-without-optimization/blob/main/User%20Specified.jpg)

Path | Flag
------------ | -------------
Linear  | 'l_shifty', 'l_zoom' and 'l_shiftx'
Newmann  |  'nl_shifty', 'nl_zoom' and 'nl_shiftx'
Great circle | 'gcircle_shifty', 'gcircle_zoom' and 'gcircle_shiftx'


## UNSUPERVISED EXPLORATION OF TRANSFORMATIONS
Linear principal directions are based on right singular vectors of the SVD on the FC weight matrix. and can be easily extracted by torch.svd() function. 
Here the flags for the first layer paths i.e., all principal directions extracted from the first weight matrix:
Path | Flag
------------ | -------------
Linear  | 'svd_linear'
Great circle | 'svd_gcircle'
Small circle | 'svd_scircle'

And here all flags relevant for the corresponding paths of other scaales:

Path | Flag
------------ | -------------
Linear  | 'linearin'
Great circle | 'greatin'
Small circle | 'smallin'

## Running examples




