# Unet_bacteria_from_DAPI
U-Net model trained for detection of bacteria on DAPI stained confocal microscopy images of human intestinal biopsies.


AWS server:
ubuntu 16.04
cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
caffe_unet_package_16.04_gpu_no_cuDNN
caffe version 1.0.0

Local machine:
Fiji ImageJ 2.0.0-rc-69/1.53c; Java 1.8.0_172


RGB images 7.2416 px/um DAPI magenta

Analyze-> Set Scale -> Remove Scale

U-Net Job Manager -> Detection on g2.2xlarge AWS, tile shape 308x308 px

Image-> Overlay-> To ROI Manager

ImageJ multipoint tool strg+left mouse botton to remove, left mouse botton to add
strg+m to count 

Save time and better performance if are with bacteria selected, copied and new image from internal clipboard

Finetune model with labeled pictures of own dataset.

excellent Tutorial
https://lmb.informatik.uni-freiburg.de/resources/opensource/unet/#detection


[1] Thorsten Falk, Dominic Mai, Robert Bensch, Özgün Çiçek, Ahmed Abdulkadir, Yassine Marrakchi, Anton Böhm, J. Deubner, Z. Jäckel, K. Seiwald, A. Dovzhenko, O. Tietz, C. Dal Bosco, S. Walsh, D. Saltukoglu, T. Tay, M. Prinz, K. Palme, M. Simons, I. Diester, Thomas Brox & Olaf Ronneberger. U-Net – Deep Learning for Cell Counting, Detection, and Morphometry. Nature Methods, 16, 67-70, 2019
