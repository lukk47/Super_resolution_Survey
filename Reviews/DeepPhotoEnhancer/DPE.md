## Short introduction
ranks 2nd in terms of SSIM and 4th in terms of PSNR in the NTIRE2018 SISR challenge, runs 5 times faster than other submissions
## Main contributions
- Augment U-Net with global features
- Improve WGAN with an adaptive weighting scheme
- Propose individual batch normalization layers for generators (better adjusting to distributions of different domains)
## Architecture
### Two-way GAN
contains a forward mapping and backward mapping and check the consistency.
![alt text](2GAN.PNG)
### Gen and Disc
![alt text](Arch.PNG)

### Loss
- L2
- Loss function:
Gen Loss:

![alt text](Gen.PNG)

Cycle consistency loss:

![alt text](Cycle.PNG)

Adversarial losses:

![alt text](Adversarial.PNG)

Gradient penalty P:

![alt text](Gradient_penalty.PNG)

### Training strategy
![alt text](Parameters_GAN.PNG)

## Experiments
- Dataset: MIT-Adobe 5K
  2250 image with retouched version for supervison training
  The other 2250 retouched image for target domain, untouched image of the first partition used as source domain
- Evaluation metric: 
- Patchsie: 512 × 512

## Final summary
### Pros:
- Global feature on Unet
- Two-way GAN with individual BN
### Cons:
- 
### Tips:
- WGAN uses the earth mover distance to measure the distance between the data distribution and the model distribution and significantly improves training stability.
- Instead of weight clipping, panalize the norm of the gradient of the discrimiator with respect to the input
- Detail comparision between different GAN models. Detailing paramenter tuning instructions
