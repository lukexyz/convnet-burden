### Report for resnet34
Model params 83 MB 

Estimates for a single full pass of model at input size 224 x 224: 

* Memory required for features: 35 MB 
* Flops: 4 GFLOPs 

Estimates are given below of the burden of computing the `features_7_2_id_relu` features in the network for different input sizes using a batch size of 128: 

| input size | feature size | feature memory | flops | 
|------------|--------------|----------------|-------| 
| 112 x 112 | 4 x 4 x 512 | 1 GB | 124 GFLOPs |
| 224 x 224 | 7 x 7 x 512 | 4 GB | 470 GFLOPs |
| 336 x 336 | 11 x 11 x 512 | 10 GB | 1 TFLOPs |
| 448 x 448 | 14 x 14 x 512 | 17 GB | 2 TFLOPs |
| 560 x 560 | 18 x 18 x 512 | 27 GB | 3 TFLOPs |
| 672 x 672 | 21 x 21 x 512 | 39 GB | 4 TFLOPs |

A rough outline of where in the network memory is allocated to parameters and features and where the greatest computational cost lies is shown below.  The x-axis does not show labels (it becomes hard to read for networks containing hundreds of layers) - it should be interpreted as depicting increasing depth from left to right.  The goal is simply to give some idea of the overall profile of the model: 

![resnet34 profile](figs/resnet34.png)
