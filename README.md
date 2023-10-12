# Video salient object detection via self-attention-guided multilayer cross-stack fusion

This repository contains the source code for the paper: Video salient object detection via self-attention-guided multilayer cross-stack fusion

## Usage

### Dependencies

- torch == 1.8+
- scipy == 1.2.2

### Training

* To train the spatial feature branch, download `TrainSet_RGB` [Google Drive Link](https://drive.google.com/file/d/1r0hzStPXFH0qJPReRjrKDdWF9xj_gw0f/view?usp=sharing) and put it `in ./data`. Run `train.py --train_type=pretrain_rgb` to start the training of the first stage

```
python train.py --train_type=pretrain_rgb
```
The generated `SMCF-19epoch.pth` file will be stored in the `./snapshot/SMCF_rgb` directory for the third stage of training.

* To train the motion feature branch, download `TrainSet_Video` [Google Drive Link](https://drive.google.com/file/d/1GHpJ9-kKx64rdNlcf68CHqNlPXeguF_W/view?usp=drive_link) and put it in `./data`. Run `train.py --train_type=pretrain_flow` to start the training of the second stage

```
python train.py --train_type=pretrain_flow
```
The generated `SMCF-19epoch.pth` file will be stored in the `./snapshot/SMCF_flow` directory for the third stage of training.

* To train the whole model, download `TrainSet_Video` (same dataset as in the second stage) and put it in `./data`. Run `train.py --train_type=finetune` to start the training of the third stage

```
python train.py --train_type=finetune
```
The generated `SMCF-19epoch.pth` file will be stored in the `./snapshot/SMCF` directory as the final training model

### 3. Testing
* The test dataset can be downloaded from:
| **Datasets**  | **Links**                                                                                                  |
|---------------|------------------------------------------------------------------------------------------------------------|
| DAVIS         | [Google Drive Link](https://drive.google.com/file/d/15ya6RbZhnkoS_QvDNGIXbwwDydwlnrZy/view?usp=drive_link) |
| DAVSOD        | [Google Drive Link](https://drive.google.com/file/d/1VysCRecOWHhI_9jwIesUwcx2dOxD881T/view?usp=drive_link) |
| DAVSOD-Normal | [Google Drive Link](https://drive.google.com/file/d/1iN1fnYoFqJX4NoHwAagIIbFxW7oY0IO4/view?usp=drive_link) |
| FBMS          | [Google Drive Link](https://drive.google.com/file/d/1JZGiQjIsa3iELWCi4H6Phe39dr0cvm7b/view?usp=drive_link) |
| MCL           | [Google Drive Link](https://drive.google.com/file/d/14VcWj0c0I6SUA4_VoZmExXXnK6LszGcu/view?usp=drive_link) |

* One can download our trained model `SMCF-19epoch.pth`, and place it in `./snapshot/SMCF`. Run `test.py` to start the testing

```
python test.py
```

### 3. Results

* The predictions of our model can be downloaded from:
| Datasets | Links                                                                                                         | 
| ---- | ----------------------------------------------------------------------------------------------------------------|
| DAVIS  | [Google Drive Link](https://drive.google.com/file/d/1YcdBroPpg_JLhxD16gZS9P9Oa1453ycD/view?usp=drive_link)  | 
| DAVSOD  | [Google Drive Link](https://drive.google.com/file/d/1avgZjyVDgLkXEgQnkshe9Jw4GquAhSrG/view?usp=drive_link) |
| DAVSOD-Normal  | [Google Drive Link](https://drive.google.com/file/d/1f-agavxm063SnzTguzlOVDnLnyrSXIJy/view?usp=drive_link) | 
| FBMS  | [Google Drive Link](https://drive.google.com/file/d/1-xiIj1q8wqb9X9wnLpOTLVFP_pbi4IlA/view?usp=drive_link) |
| MCL  | [Google Drive Link](https://drive.google.com/file/d/1n0svfFhcScTpPZG5MdLsHOq5blK0GnJ3/view?usp=sharing) |


## Method Detials
![](./png/model.png)


## Cite
If you find our code useful for your research, please cite our paper:

H. Yang, N. Mu, J. Guo, Y. Hu, and R. Wang, "Video salient object detection via self-attention-guided multilayer cross-stack fusion", Multimedia Tools and Applications, 2023.

In case of any questions, please contact the corresponding author N. Mu at nanmu@sicnu.edu.cn
