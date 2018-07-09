# Optical Flow Guided Feature: A Fast and Robust Motion Representation for Video Action Recognition

![ ](head_pic.jpg)

### Update
We've just release the code as an initial version. Further code, docs, models and training recipes will be available VERY soon.

---

This repo holds the implementation code of the paper:

[Optical Flow Guided Feature: A Fast and Robust Motion Representation for Video Action Recognition](http://openaccess.thecvf.com/content_cvpr_2018/papers/Sun_Optical_Flow_Guided_CVPR_2018_paper.pdf), [Shuyang Sun](https://kevin-ssy.github.io/), [Zhanghui Kuang](http://jeffreykuang.github.io/index.html), [Lu Sheng](http://www.ee.cuhk.edu.hk/~lsheng/), [Wanli Ouyang](https://wlouyang.github.io/), [Wei Zhang](), CVPR 2018.

### Prerequisites
- OpenCV 2.4.12
- OpenMPI 1.8.5 (enable-thread-multiple when install)
- CUDA 7.5
- CUDNN 5
- [Caffe Dependencies](http://caffe.berkeleyvision.org/install_apt.html)

You may refer to the project [TSN](https://github.com/yjxiong/temporal-segment-networks) to install these libs and prepare the data.

### Building Docs

For training use, first modify the file **make_train.sh** with your own lib path filled in. Simply run ```sh make_train.sh```, the script will automatically build the caffe for you.

For testing, you can simply run ```make pycaffe``` to make all stuff well prepared.

### Training
You need to make two folders before you launch your training. The one is ```logs``` under the root of this project, and the other is the ```model``` under the folder ```models/DATASET/METHOD/SPLIT/```. For instance, if you want to train ```RGB_OFF``` on the dataset ```UCF101 split 1```, then your dir should be made under the path ```models/ucf101/RGB_OFF/1/```. The models for initialization and the training recipes will be available soon.

### Testing
You need to create another directory ```proto_splits``` under the same folder of ```model```. Our test code use pycaffe to call the functions defined in C++, therefore, we need to write some temporary files for synchronization. Remember to clean the temporary files everytime you make a new test.

### Results
Due to the unexpected server migration, the original models for all 3 splits on UCF101 and HMDB51 were all lost. Therefore, we re-train the models on the first split of UCF101:

| RGB | OFF(RGB) | RGB DIFF | OFF(RGB DIFF) |   FLOW  | OFF(FLOW) |   Acc.  | 
| :-: |    :-:   |    :-:   |      :-:      |   :-:   |    :-:    |   :-:   |
|<ul><li>[x] </li></ul>|<ul><li>[x] </li></ul>|<ul><li>[ ] </li></ul>|<ul><li>[ ] </li></ul>|<ul><li>[ ] </li></ul>|<ul><li>[ ] </li></ul>|  89.9%  |
|<ul><li>[x] </li></ul>|<ul><li>[x] </li></ul>|<ul><li>[x] </li></ul>|<ul><li>[x] </li></ul>|<ul><li>[ ] </li></ul>|<ul><li>[ ] </li></ul>|  93.1%  |
| <ul><li>[x] </li></ul> |<ul><li>[x] </li></ul>|<ul><li>[ ] </li></ul>|<ul><li>[ ] </li></ul>|<ul><li>[x] </li></ul>|<ul><li>[x] </li></ul>|  95.4%  |



### Release Schedule
- [x] Paper Link
- [x] Network Prototxt
- [x] Testing Code
- [x] Training Code
- [ ] Pretrained Models
- [ ] Training Recipes
- [ ] Building Docs

### Citation
If you find our research useful, please cite the paper:
```
@InProceedings{Sun_2018_CVPR,
author = {Sun, Shuyang and Kuang, Zhanghui and Sheng, Lu and Ouyang, Wanli and Zhang, Wei},
title = {Optical Flow Guided Feature: A Fast and Robust Motion Representation for Video Action Recognition},
booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
month = {June},
year = {2018}
}
```

### Related Project
[Temporal Segment Networks](https://github.com/yjxiong/temporal-segment-networks)
