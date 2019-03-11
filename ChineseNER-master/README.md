## Recurrent neural networks for Chinese named entity recognition in TensorFlow
This repository contains a simple demo for chainese named entity recognition.


## Requirements
- [Tensorflow=1.2.0](https://github.com/tensorflow/tensorflow)
- [jieba=0.37](https://github.com/fxsjy/jieba)


## Model
The model is a birectional LSTM neural network with a CRF layer. Sequence of chinese characters are projected into sequence of dense vectors, and concated with extra features as the inputs of recurrent layer, here we employ one hot vectors representing word boundary features for illustration. The recurrent layer is a bidirectional LSTM layer, outputs of forward and backword vectors are concated and projected to score of each tag. A CRF layer is used to overcome label-bias problem.

Our model is similar to the state-of-the-art Chinese named entity recognition model proposed in Character-Based LSTM-CRF with Radical-Level Features for Chinese Named Entity Recognition.

## Basic Usage

### Default parameters:
- batch size: 20
- gradient clip: 5
- embedding size: 100
- optimizer: Adam
- dropout rate: 0.5
- learning rate: 0.001

Word vectors are trained with gensim version of word2vec on Chinese WiKi corpus(https://github.com/sea2603).

### Train the model with default parameters:
```shell
$ python3 main.py --train=True --clean=True

```

### Online evaluate:
```shell
$ python3 main.py
```


