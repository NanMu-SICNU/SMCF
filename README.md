# Video salient object detection via self-attention-guided multilayer cross-stack fusion

This repository contains the source code for the paper: Video salient object detection via self-attention-guided multilayer cross-stack fusion

## Usage

### Dependencies

- torch == 1.8+
- scipy == 1.2.2

### Training

* To train the spatial feature branch, download `TrainSet_RGB` and put it `in ./data`. Run `train.py --train_type=pretrain_rgb` to start the training of the first stage

```
python train.py --train_type=pretrain_rgb
```
The generated `SMCF-19epoch.pth` file will be stored in the `./snapshot/SMCF_rgb` directory for the third stage of training.

* To train the motion feature branch, download `TrainSet_Video` and put it in `./data`. Run `train.py --train_type=pretrain_flow` to start the training of the second stage

```
python train.py --train_type=pretrain_flow
```
The generated `SMCF-19epoch.pth` file will be stored in the `./snapshot/SMCF_flow` directory for the third stage of training.

* To train the whole model, download `TrainSet_Video` (same dataset as in the second stage) and put it in `./data`. Run `train.py --train_type=finetune` to start the training of the third stage

```
python train.py --train_type=finetune
```
The generated `SMCF-19epoch.pth` file will be stored in the `./snapshot/SMCF` directory as the final training model.

### 3. Testing
* One can download our trained model `SMCF-19epoch.pth`, in `./snapshot/SMCF`. Run `test.py` to start the testing

```
python test.py
```

### 3. Results



## Method Detials
![](./png/model.png)


## Cite
If you find our code useful for your research, please cite our paper:

H. Yang, N. Mu, J. Guo, Y. Hu, and R. Wang, "Video salient object detection via self-attention-guided multilayer cross-stack fusion", Multimedia Tools and Applications, 2023.

In case of any questions, please contact the corresponding author N. Mu at nanmu@sicnu.edu.cn
