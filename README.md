# Cows2021
This repository contains the source code that accompanies our paper "Towards Self-Supervision for Video Identification of Individual Holstein-Friesian Cattle: The Cows2021 Dataset" at: https://arxiv.org/abs/2105.01938. At its core, the code in this repository is adapted and extended (with permission) from William Andrew et al's work on "Visual Identification of Individual Holstein Friesian Cattle via Deep Metric Learning" published in Computers and Electronics in Agriculture 2021 -- [paper](https://arxiv.org/pdf/2006.09205.pdf), [source code](https://github.com/CWOA/MetricLearningIdentification) 

The trained weights from the for cow detection and identification are included in this repository at `weights/`.


## Installation
1) Clone this repository.
2) Install any missing requirements via pip or conda: [numpy](https://pypi.org/project/numpy/), [PyTorch](https://pytorch.org/), [OpenCV](https://pypi.org/project/opencv-python/), [Pillow](https://pypi.org/project/Pillow/), [tqdm](https://pypi.org/project/tqdm/), [sklearn](https://pypi.org/project/scikit-learn/), [seaborn](https://pypi.org/project/seaborn/). This repository requires python 3.6+
3) Instead of installing `pycocotools`, use the pycocotools in this repository.

## Usage

### Video Processing
Run the code in `make_data` one by one to obtain the training images for individual identification. The trained model weight of detection can be found `Sub-levels/3Weights/trained_model/resnet50_trained_144.h5` from [here](https://data.bris.ac.uk/data/dataset). Alternatively, you can [download](https://data.bris.ac.uk/data/dataset) this data from `Sub-levels/2Identification`. 

### Individual Identification
#### Testing
To test a trained model by inferring embeddings and using GMM to obtain the accuracy, run the code in `Test` one by one.

#### Training
To train the model, use python train.py -h to get help with setting command line arguments. A minimal example would be python train.py --out_path=output/ --folds_file=datasets/OpenSetCows2020/splits/10-90.json.

## Citation

Consider citing ours and William's works in your own research if this repository has been useful:

```
@article{gao2021towards,
  title={Towards Self-Supervision for Video Identification of Individual Holstein-Friesian Cattle: The Cows2021 Dataset},
  author={Gao, Jing and Burghardt, Tilo and Andrew, William and Dowsey, Andrew W and Campbell, Neill W},
  journal={arXiv preprint arXiv:2105.01938},
  year={2021}
}

@article{andrew2020visual,
  title={Visual Identification of Individual Holstein Friesian Cattle via Deep Metric Learning},
  author={Andrew, William and Gao, Jing and Campbell, Neill and Dowsey, Andrew W and Burghardt, Tilo},
  journal={arXiv preprint arXiv:2006.09205},
  year={2020}
}
```

![Footer](https://github.com/Wormgit/Cows2021/tree/main/images/ids.png)
