## Short introduction
Using recursive-supervision and skip-connection, combining all predictions resulting from different levels of recursions to deliver a more accurate final prediction.
## Main contributions
- recursive-supervision
- skip-connection

## Architecture

### Basic model
![alt text](Arch.PNG)

### Recursive unit
![alt text](R_unit.PNG)

### Advanced model
![text](Ad_arch.PNG)

### Loss
- Loss function: MSE

	- Intermediate loss

	![alt text](Loss_inter.PNG)

	- Final output loss
	
	![alt text](Loss_final.PNG)

	- Final loss
	
	![alt text](Loss_all.PNG)

### Training strategy
- Starts by training only the 2× portion of the network
- Incrementally add training pairs of the next scale
- Randomly select one of the scales s to avoid mixing batch statistics

## Experiments
- Dataset: 91 image, set5, set14, B100


## Final summary
### Pros:
- Better training and architecture for better results
### Cons:
- 
### Tips:


