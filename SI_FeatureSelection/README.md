# Auto-encoder Feature Selection with SI

## Seperation Index(SI)

Seperation Index (SI) is a seperating measure in classification problems. It shows that how much input data points seperate the labels from eachother.
We can use SI for feature selection, the feature that creates more SI is more informative.<br/>
Below is the SI Formula: <br/>
<img src="imgs/SI-formula.png" data-canonical-src="img/SI-formula.png" width="400" /><br/>


## Dataset
We use CIFAR10 and CIFAR100 for training and inference.

## Training
We compare result with five different methods:
- Auto-encoder with VGG16 backbone on CIFAR10
- Auto-encoder with Convolutional layers on CIFAR10
- Pretrained VGG16 on CIFAR10
- Variational Auto-Encoder on CIFAR10
- Variational Auto-encoder on CIFAR100

## Resualts

|  Row |  model    | Dataset |  latent space features | selected features| SI on latent space features| SI on selected features|SI changes|
| -----|-----------|---------|------------------------|------------------|----------------------------|------------------------|----------|
|   1  |Auto-encoder with VGG16 backbone|CIFAR10|2048|2|0.0853|0.138|increase 0.053|
|   2  |Auto-encoder with convolutional layers|CIFA10|384|25|0.2918|0.30|increase 0.0082|
|   3  |Pretrained VGG16| CIFAR10 | 8192|100|0.5921|0.55|decrease 0.0421|
|   4  |Variational Auto-encoder|CIFAR10|256|65|0.7404|0.755|increase 0.0146|
|   5  |Variational Auto-encoder|CIFAR100|256|20|0.6832|0.691|increase 0.0078|
