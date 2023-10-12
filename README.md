# Video salient object detection via self-attention-guided multilayer cross-stack fusion

This repository contains the source code for the paper: Video salient object detection via self-attention-guided multilayer cross-stack fusion

## Usage

### Dependencies

- torch == 1.8+
- scipy == 1.2.2

### Training

* Run `train.py --train_type=pretrain_rgb` to start the training of the first stage

```
python train.py --train_type=pretrain_rgb
```

* Run `train.py --train_type=pretrain_flow` to start the training of the second stage

```
python train.py --train_type=pretrain_flow
```

* Run `train.py --train_type=finetune` to start the training of the third stage

```
python train.py --train_type=finetune
```

### 3. Testing
* Run `test.py` to start the testing

```
python test.py
```




## Method Detials
![](./png/model.png)


## Cite
If you find our code useful for your research, please cite our paper:

H. Yang, N. Mu, J. Guo, Y. Hu, and R. Wang, "Video salient object detection via self-attention-guided multilayer cross-stack fusion", Multimedia Tools and Applications, 2023.

In case of any questions, please contact the corresponding author N. Mu at nanmu@sicnu.edu.cn
