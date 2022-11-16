# 1. Prepare envrionment

1) create a virtual env
2) install dependencies

```
pip install -r requirements.txt
```

3) determine cuda is available 

```
python -c "import torch; print(torch.cuda.is_available())"
```

# 2. Download Dataset

1) download agnews
```
python download_agnews.py
```
data will save to `data/agnews`

2) download arxiv
```
python download_arxiv.py
```
data will save to `data/arxiv-clf`

# 2. Train Baseline

TODO:

- [ ] AGNews
- [ ] Arxiv


## AGNews

### Lonformer

```
CUDA_VISIBLE_DEVICES=0 python train.py --model_name longformer --data agnews --batch_size 8 --epochs 20 --lr 5e-05 --scheduler
```


## Arxiv

### longformer 

```
CUDA_VISIBLE_DEVICES=0 python train.py --model_name longformer --data arxiv --batch_size 8 --epochs 20 --lr 3e-05 --scheduler
```


### tobert

```
CUDA_VISIBLE_DEVICES=0 python train.py --model_name tobert --data arxiv --batch_size 8 --epochs 20 --lr 3e-05
```
