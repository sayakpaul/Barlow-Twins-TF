# Barlow-Twins-TF

<div align="center">
<a href="https://colab.research.google.com/github/sayakpaul/Barlow-Twins-TF/blob/main/Barlow_Twins.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
</div><br>

This repository implements **Barlow Twins** ([Barlow Twins: Self-Supervised Learning via Redundancy Reduction](https://arxiv.org/abs/2103.03230)) in TensorFlow and demonstrates it on the CIFAR10 dataset.

**Summary**:

With a ResNet20 as a trunk and a 3-layer MLP (each layer containing 2048 units) and 100 epochs of pre-training, [this training notebook](https://github.com/sayakpaul/Barlow-Twins-TF/blob/main/Barlow_Twins.ipynb) can give **62.61%** accuracy on the CIFAR10 test set. The pre-training total takes ~23 minutes on a single Tesla V100. There are minor differences from the [original implementation](https://github.com/facebookresearch/barlowtwins/). However, the original loss function and the other minor details like having a big enough projection dimension have been maintained.

For details on Barlow Twins, I suggest reading the original paper, it's really well-written. 

## Loss progress during pre-training

<div align="center">
  <img src="https://i.ibb.co/9Y0STVZ/image.png"></img>
</div>

## Other notes
* Pre-trained model is available [here](https://github.com/sayakpaul/Barlow-Twins-TF/releases/download/v1.0.0/barlow_twins.tar.gz). 
* To follow the original implementation details as closely as possible, a WarmUpCosine learning rate schedule has been used during pre-training:
  
  <div align="center">
    <img src="https://i.ibb.co/khbLyvZ/image.png"></img>
  </div>
* During linear evaluation, Cosine Decay has been used. 

## Acknowledgements

Thanks to Stéphane Deny (one of the authors of the paper) for helping me catch a pesky bug.
