# U-net based quantification of bacteria

U-Net provides a straightforward ImageJ plugin that can be used for deep learning based detection and quantification tasks [<sup>[1]<sup>](#1).
We used U-Net to help us quantify bacteria on hundrets of DAPI stained confocal microscopy images of cuts from methacarn-fixed human intestinal biopsies.

## Methodology for the manuscript

The standard model ([2d_cell_net_v0.caffemodel.h5](https://lmb.informatik.uni-freiburg.de/resources/opensource/unet/2d_cell_net_v0_model.zip))[<sup>[1]<sup>](#1) was finetuned with the annotated dataset in the [training_set](training_set/) folder.

The resulting model and weight files used for the manuscript are:
-  [unet-0ce131a1-8282-464a-9b8a-e2a6a4777166.modeldef.h5](unet-0ce131a1-8282-464a-9b8a-e2a6a4777166.modeldef.h5)
-  [finetuned_3.caffemodel.h5](finetuned_3.caffemodel.h5)

Data from supplementary figure S1d can be reproduced with these model and weight files and [Figure_S1_Example.tif](figure_S1/Fig_S1_Example.tif) (a representative image which was not part of the training set).

### Software versions used

Calculations were done on an g2.2xlarge AWS server:\
ubuntu 16.04\
cuda-repo-ubuntu1604_8.0.61-1_amd64.deb\
caffe_unet_package_16.04_gpu_no_cuDNN\
caffe version 1.0.0\
u-net detection tile shape: 308x308 px

Local machine:\
Fiji ImageJ 2.0.0-rc-69/1.53c; Java 1.8.0_172

## Applying the model to your own data

Our model and weight files can be used for similar projects:

- images must be 7.2416 px/um, in RGB with DAPI signal as magenta.
- Analyze-> Set Scale-> Remove Scale
- U-Net Job Manager-> Detection
- Image-> Overlay-> To ROI Manager
- ImageJ multipoint tool; strg+left mouse botton to remove, left mouse botton to add datapoints
- strg+m to count total amount of bacteria in the image

To save time and for better performance select and copy the area with bacteria and perform detection on a new image from the internal clipboard.

It is recommended to finetune the weight file with a couple of annotated images of your own dataset.
For an excellent tutorial on setting up U-net, finetuning and detection visit the [original u-net project](https://lmb.informatik.uni-freiburg.de/resources/opensource/unet/#detection).

## References
<a id="1">[1]</a>
Thorsten Falk, Dominic Mai, Robert Bensch, Özgün Çiçek, Ahmed Abdulkadir, Yassine Marrakchi, Anton Böhm, J. Deubner, Z. Jäckel, K. Seiwald, A. Dovzhenko, O. Tietz, C. Dal Bosco, S. Walsh, D. Saltukoglu, T. Tay, M. Prinz, K. Palme, M. Simons, I. Diester, Thomas Brox & Olaf Ronneberger. U-Net – Deep Learning for Cell Counting, Detection, and Morphometry. Nature Methods, 16, 67-70, 2019
