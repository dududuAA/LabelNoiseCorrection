# Official PyTorch implementation for the ICML 2019 paper: "Unsupervised label noise modeling and loss correction"
Original corrupted images used for training             |  Network prediciton post training
:-------------------------:|:-------------------------:
![couldn't find image](https://github.com/PaulAlbert31/LabelNoiseCorrection/blob/master/data/1000before.png)  | ![couldn't find image](https://github.com/PaulAlbert31/LabelNoiseCorrection/blob/master/data/1000after.png)

You can find in [RunScripts.sh](https://github.com/PaulAlbert31/LabelNoiseCorrection/blob/master/RunScripts.sh) an example script to run the code for 80% label noise (M-DYR-H and M-DYR-S) and 90% label noise (MD-DYR-SH).

Feel free to modify input parameters for any level of label noise (and other parameters in the paper).

Additionally, the code is now supporting both CIFAR-10 and CIFAR-100 but feel free to adapt it for other datasets such as TinyImagenet by changing the data loaders and modifying the noise addition function in [utils.py](https://github.com/PaulAlbert31/LabelNoiseCorrection/blob/master/utils.py#53)

 | Dependencies  |
| ------------- |
| python == 3.6     |
| pytorch == 0.4.1     |
| cuda92|
| torchvision|
| matplotlib|
| scikit-learn|
| tqdm|

### Environement
If you are unsing conda, you can execute:
```sh
$ conda env create -f environment.yml
$ conda activate lnoise
```
This will include all dependencies in a new conda environement called lnoise

### Supported datasets:
CIFAR-10 & CIFAR-100 datasets are currtently supported and will be downloaded automatically to the path set with --dataset option

### We run our approach on:
CPU: Intel(R) Core(TM) i7-6850K CPU @ 3.60GHz GPU: NVIDIA GTX1080Ti

### Parameters details
Please execute the following to get details about parameters. Most of them are correctly set by default to get the best possible final accuracy.
``` sh
$ python train.py --h
```

Note: We thank authors from [1](https://github.com/facebookresearch/mixup-cifar10) for the mixup and Pytorch implementation of PreAct ResNet (https://github.com/facebookresearch/mixup-cifar10) \
that we use in our code.

[1] Hongyi Zhang, Moustapha Cisse, Yann N. Dauphin, David Lopez-Paz, "mixup: Beyond Empirical Risk Minimization", in International Conference \
on Learning Representations (ICLR), 2018.