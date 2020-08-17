# Haar Graph Pooling
This repository is the official implementation of [Haar Graph Pooling (Wang et al., ICML 2020)](https://arxiv.org/abs/1909.11580). 

![HaarPooling idea](HaarPool_idea.png)


## Requirements

To install requirements:

```setup
pip install -r requirements.txt
```

## Training and Evaluation

To train and test the model(s) in the paper, run the following command. We provide the codes for HaarPool on five graph classification benchmarks in Table 1. The dataset will be automatically downloaded and preprocessed before training. All the experiments were performed using [PyTorch Geometric](https://github.com/rusty1s/pytorch_geometric) and run on a server with Intel(R) Core(TM) i9-9820X CPU 3.30GHz, NVIDIA GeForce RTX 2080 Ti.

HaarPool on Graph classification benchmark datasets; dataname to be replaced by PROTEINS, PROTEINS_full, NCI1, AIDS, Mutagenicity
```
python pan_benchmark.py --dataname --L 3 --runs 10
```
PAN on PointPattern classification task
```
python pan_pointpattern.py --phi 0.3 --L 4 --runs 10
```
Other hyperparameters: --batch_size, --learning_rate, --weight_decay, --pool_ratio, --nhid, --epochs

## Results

Our model PAN achieves the following performance on graph classification benchmark datasets MUTAG, PROTEINSF and NCI1, and our new graph classification dataset PointPattern (with phi=0.35). The table below shows the mean test accuracy with SD for 10 repetitions. Compared to existing methods such as GCNConv+TopKPool, SAGEConv+SAGPool, GATConv+EdgePool, with the same network architecture, the PAN achieves top test accuracy on most of these datasets. The results are obtained using the above .py programs. The test results on other benchmarks and comparison with the results of other methods can be seen in the paper.

![PAN results](pan_results.png)

## Citation 
If you use our codes and datasets, please cite:
```
@article{wang2020haar,
  title={Haar Graph Pooling},
  author={Sloan, Ian H. and Le Gia, Quoc T. and and Wang, Yu Guang and Womersley, Robert S. and Hamann, Jan},
  journal={arXiv preprint arXiv:},
  year={2019}
}
```

## Contributing
Copyright (c) <2020> <NeurIPS>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
