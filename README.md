# GaIA: Graphical Information Gain based Attention Network for Weakly Supervised Point Cloud Semantic Segmentation (WACV 2023)
[![arXiv](https://img.shields.io/badge/arXiv-2210.01558-b31b1b.svg)](https://arxiv.org/abs/2210.01558)

## Updates
* <h2> [Oct.11] Full implementation is updated soon. </h2>

## Installation
### Requirements
* python >= 3.7.0
* torch >= 1.8.0


### Install `Spconv`
* To compile `spconv`, install the dependent libraries. 
```
pip install spconv-cu111
```


Add the `$LD_LIBRARY_PATH` to `~/.bashrc`.
```
export TORCH_CUDA_ARCH_LIST="8.0"
```

### Install `pointgroup_ops`
* Compile the `pointgroup_ops` library.
```
cd lib/pointgroup_ops
python setup.py develop
```

### Install `pointops`
* Compile the `pointops` library.
```
cd lib/pointops
python setup.py develop
```


## Data Preparation

* Download the [ScanNet-v2](http://www.scan-net.org/) dataset.

* Put the data in the corresponding folders. 

* Put the file `scannetv2-labels.combined.tsv` in the `data/` folder.

* Run the script `scannet_preprocess.py`.


## Training GaIA

* Set the data_root/dataset in config/scannet.yaml

```
## training ScanNet-v2 dataset
python train.py --config config/scannet.yaml 
```


## Inference

* ScanNet-v2 dataset evaluation with validation set

```
## set the test_epoch
python test.py --config config/scannet.yaml --test_epoch ***
```

* ScanNet-v2 evaluation with official test set

```
## Set validation: False in scannet.yaml
python test.py --config config/scannet.yaml --test_epoch ***
```


## Citation
<pre><code>
@article{lee2022gaia,
  title={GaIA: Graphical Information Gain based Attention Network for Weakly Supervised Point Cloud Semantic Segmentation},
  author={Lee, Min Seok and Yang, Seok Woo and Han, Sung Won},
  journal={arXiv preprint arXiv:2210.01558},
  year={2022}
}
</code></pre>
