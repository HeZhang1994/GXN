# GXN

Graph Cross Networks with Vertex Infomax Pooling (NeurIPS 2020) [paper](https://arxiv.org/abs/2010.01804)

![image](https://github.com/limaosen0/GXN/blob/main/images/GXNstructure.png)

We propose a novel graph cross network (GXN) to achieve comprehensive feature learning from multiple scales of a graph. Based on trainable hierarchical representations of a graph, GXN enables the interchange of intermediate features across scales to promote information flow. Two key ingredients of GXN include a novel vertex infomax pooling (VIPool), which creates multiscale graphs in a trainable manner, and a novel feature-crossing layer, enabling feature interchange across scales. The proposed VIPool selects the most informative subset of vertices based on the neural estimation of mutual information between vertex features and neighborhood features. The intuition behind is that a vertex is informative when it can maximally reflect its neighboring information. The proposed feature-crossing layer fuses intermediate features between two scales for mutual enhancement by improving information flow and enriching multiscale features at hidden layers. The cross shape of the feature-crossing layer distinguishes GXN from many other multiscale architectures. Experimental results show that the proposed GXN improves the classification accuracy by 1.96% and 1.15% on average for graph classification and vertex classification, respectively. Based on the same network, the proposed VIPool consistently outperforms other graph-pooling methods.

Here we show the codes of GXN for graph classification as an example.

## Module Requirement
* Python 3.6
* Pytorch 1.1
* numpy

## Installation
This implementation is under the "lib/" directory, run
```
make -j4
```
to compile the necessary C++ files. After compiling the dependent files, you can go to the root directory and run
```
sh run_GXN.sh [DATANAME] [DATAFOLD] [GPUNUM]
```
If you want to train and test a model on COLLAB dataset, you should first unzip files, because the original file is large - for convenience, we upload the compressed file directly. Type
```
cd ./GraphClassificationData/COLLAB
unzip COLLAB.zip
```



## Acknowledgement
Our program is built based on the code of [DGCNN](https://github.com/muhanzhang/pytorch_DGCNN) and [Graph U-Nets](https://github.com/HongyangGao/Graph-U-Nets). We appreciate their contribution on the technique development and released codes.

