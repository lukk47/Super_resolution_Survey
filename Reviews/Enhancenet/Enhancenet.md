## Short introduction
Intergration of all losses inclduing perceptual, texture and adversarial losses. Detial comparsion are given.
## Main contributions
- Combination of three losses
## Architecture
### Generator
![alt text](Gene.PNG)

### Discriminator
![alt text](Disc.PNG)

### Loss
- Three loss functions including perceptual, texture and adversarial losses
- Using perceptual loss (vgg16: pool2, pool4).

- Loss function:
	- Perceptual loss:
	![alt text](Perc_loss.PNG)
	Feature extracted from pretrained vgg19
	Combination of 2th and 5th pooling layers
	MSE
	- Texture loss:
	![alt text](Text_loss.PNG)
	Patch size 16X16
	Conv layers of first three groups in VGG
	- Adversarial loss:
	![alt text](adverasrial_training.PNG)

### Training strategy
- Starts by training only the 2× portion of the network
- Incrementally add training pairs of the next scale
- Randomly select one of the scales s to avoid mixing batch statistics

## Experiments
- Dataset: All color images in coco with at least 384 pixels on the short
Roughly 200k images
Cropped and downsampled to 256
Size of input to 32X32
- Adam, learning rate 0.0001

## Final summary
### Pros:
- Great perceptual performance
### Cons:
- Gan will bring in weried artifical detials
### Tips:
- Balance between different losses have a great effect and need careful finetune.

