# CPSC488_Project
Extension of GreaseLM: https://github.com/snap-stanford/GreaseLM/tree/main

See modeling_greaselm_head.py for my edited version of modeling_greaselm.py.

Data:

From https://drive.google.com/drive/folders/1T6B4nou5P3u-6jr0z6e3IkitO8fNVM6f, download medqa_usmle_model.pt (for GreaseLM's model) and data_preprocessed_biomed.zip, which should both be placed within the same top level of this folder.

Computing Environment and How to Run:
Log onto a cluster (I used Grace). Git clone repo.
Requires 1 GPU, with 32G memory. Takes around 7-8 hours to train.
```
salloc --partition=gpu_devel --time=7:00:00 --mem=32G -c4 --gpus=rtx5000
module load miniconda
conda activate greaselm
ml CUDA/10.1.243 GCC/12.2.0
cd CPSC488_Project
```

Frameworks and Packages:
```
conda create -y -n greaselm python=3.8
conda activate greaselm
pip install numpy==1.18.3 tqdm
pip install torch==1.8.0+cu101 torchvision -f https://download.pytorch.org/whl/torch_stable.html
pip install transformers==3.4.0 nltk spacy
pip install wandb
conda install -y -c conda-forge tensorboardx
conda install -y -c conda-forge tensorboard

# for torch-geometric
pip install torch-scatter==2.0.7 -f https://pytorch-geometric.com/whl/torch-1.8.0+cu101.html
pip install torch-cluster==1.5.9 -f https://pytorch-geometric.com/whl/torch-1.8.0+cu101.html
pip install torch-sparse==0.6.9 -f https://pytorch-geometric.com/whl/torch-1.8.0+cu101.html
pip install torch-spline-conv==1.2.1 -f https://pytorch-geometric.com/whl/torch-1.8.0+cu101.html
pip install torch-geometric==1.7.0 -f https://pytorch-geometric.com/whl/torch-1.8.0+cu101.html
```

Python == 3.8
PyTorch == 1.8.0
transformers == 3.4.0
torch-geometric == 1.7.0


