# [CVPR2022]Learning Optical Flow with Kernel Patch Attention

<h4 align="center">Ao Luo<sup>1</sup>, Fan Fang<sup>2</sup>, Xin Li<sup>2</sup>, Shuaicheng Liu<sup>3,1</sup></h4>
<h4 align="center">1. Megvii Research,             2. Group 42</h4>
<h4 align="center">3. University of Electronic Science and Technology of China</h4>

This project provides the official implementation of '[**Learning Optical Flow with Kernel Patch Attention**](https://openaccess.thecvf.com/content/CVPR2022/papers/Luo_Learning_Optical_Flow_With_Kernel_Patch_Attention_CVPR_2022_paper.pdf)'. (CVPR-2022)

## Abstract
Optical flow is a fundamental method used for quantitative motion estimation on the image plane. In the deep learning era, most works treat it as a task of ‘matching of features’, learning to pull matched pixels as close as possible in feature space and vice versa. However, spatial affinity (smoothness constraint), another important component for motion understanding, has been largely overlooked. In this paper, we introduce a novel approach, called kernel patch attention (KPA), to better resolve the ambiguity in dense matching by explicitly taking the local context relations into consideration. Our KPA operates on each local patch, and learns to mine the context affinities for better inferring the flow fields. It can be plugged into contemporary optical flow architecture and empower the model to conduct comprehensive motion analysis with both feature similarities and spatial relations. On Sintel dataset, the proposed KPA-Flow achieves the best performance with EPE of 1.35 on clean pass and 2.36 on final pass, and it sets a new record of 4.60% in F1-all on KITTI-15 benchmark.

## Presentation Video
[[Youtube](https://www.youtube.com/watch?v=2x1nkue8aEA)], [[Bilibili](https://www.bilibili.com/video/BV1D341137iA/)]


## Overview

We propose a novel approach, called kernel patch attention (KPA), to better resolve ambiguity in dense matching by explicitly taking the local context relations into consideration. Our KPA operates on each local patch, and learns to mine the context affinities for better inferring the flow fields. It can be plugged into contemporary optical flow architecture and empower the model to conduct comprehensive motion analysis with both feature similarities and spatial relations.

![KPA_overview](https://user-images.githubusercontent.com/47421121/175027700-d267dd6b-2208-41d9-b875-9d33653a8d48.png)

## Requirements

Python 3.6 with following packages
```Shell
pytorch==1.6.0
torchvision==0.7.0
matplotlib
scipy
opencv-python
tensorboard
```
(The code has been tested on Cuda 10.0.)


## Usage

1. The trained weights are available on [GoogleDrive](https://drive.google.com/drive/folders/1rt8q7EkbeWoivTxijtPJbOsdwGYctYt_?usp=sharing). Put `*.pth` files into folder `./weights`.

2. Download [Sintel](http://sintel.is.tue.mpg.de/) and [KITTI](http://www.cvlibs.net/datasets/kitti/eval_scene_flow.php?benchmark=flow) dataset, and set the root path of each class in `./core/datasets.py`.


3. Evaluation on Sintel
```Shell
./eval_sintel.sh
```

4. Evaluation on KITTI
```Shell
./eval_kitti.sh
```
We extend our approach by appending the simplified KPA module to the encoder network. Experimental results demonstrate that the extended version achieves better performance than the original one.


## Results
![results](https://user-images.githubusercontent.com/1344482/181144487-2206ec5a-defc-48f9-a000-d742959c7e50.JPG)

## Citation

If you think this work is helpful, please cite
```
@inproceedings{luo2022learning,
  title={Learning Optical Flow With Kernel Patch Attention},
  author={Luo, Ao and Yang, Fan and Li, Xin and Liu, Shuaicheng},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={8906--8915},
  year={2022}
}

```

If you have any questions, please contact me at (aoluo_uestc@hotmail.com).

## Acknowledgement

The main framework is adapted from [RAFT](https://github.com/princeton-vl/RAFT). We thank the authors for the contribution.
