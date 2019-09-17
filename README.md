# Improved Embeddings with Easy Positive Triplet Mining

This repository contains a PyTorch(1.1.0) implementation of Improved Embeddings with Easy Positive Triplet Mining(WACV2020)

Paper link: https://arxiv.org/abs/1904.04370

Prepare the training data and testing data in python dictionary format. 

For example:
```
data_dict = {'tra' : {'class_tra_01':[image path list],
                      'class_tra_02':[image path list],
                      'class_tra_03':[image path list],
                      ....,
                      'class_tra_XX':[image path list]}
                 
             'test': {'class_test_01':[image path list],
                      'class_test_02':[image path list],
                      'class_test_03':[image path list],
                      ....,
                      'class_test_XX':[image path list]}
            }
```
                 

Replace Data and data_dict in the file ```main.py```

We only have the color nomarlization info for CUB, CAR, SOP, In-shop cloth, and PKU vehicleID data. If you use other dataset please add the color nomarlization data in the file: ```_code/color_lib.py```

We also supply our efficient recall@K accuracy calculation functions which are located in ```_code/Utils.py```

```
This function is for CAR,CUB and SOP dataset
recall(Fvec, imgLab,rank=None) 
Fvec:   Feature vectors, N by D torch.Tensor
imgLab: Image label, python list
rank:   k of recall@k, python list

This function is for In-shop Cloth dataset
recall2(Fvec_val, Fvec_gal, imgLab_val, imgLab_gal,rank=None) 
Fvec_val:     Probe feature vectors, N_val by D torch.Tensor
Fvec_gal:     Gallary feature vectors, N_gal by D torch.Tensor
imgLab_val:   Probe image label, python list
imgLab_gal:   Gallary image label, python list
rank:         k of recall@k, python list
```

The example of calling the function is shown in  ```Recall.ipynb```

Please cite our paper, if you use these functions for recall calculation.

### Requirements
Pytorch 1.0.0

Python 3.7

### Updates

### Citation
```
@article{Xuan2019ImprovedEW,
  title={Improved Embeddings with Easy Positive Triplet Mining},
  author={Hong Xuan and Abby Stylianou and Robert Pless},
  journal={ArXiv},
  year={2019},
  volume={abs/1904.04370}
}
```