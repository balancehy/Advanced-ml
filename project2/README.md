This project mainly aims to use different approaches to verify the writer of handwritting images. 

## Task 2 Bayesian network
Use structural learning to find best Bayesian structure given the 15 annotated features one handwriting image. In order to 
verify whether two given images are written by the same writer, the same Bayesian network structure is used for the two images and a verification node which has binary value is created. So there are totally 31 feature node in the full Bayesian network. One or more correspondant node pairs in the networks of two images are conneted to the verificaiton node. For example, 12th nodes in both networks are linked to the verification node. 

The full network is trained by Maximumlikelihood esitimator to get all CPDs. Then, it can proceed query tasks: input 15 times 2 feature values to the network, and output a binary value from verification node.

## Task 3 Deep learning approach
A Siamese network is used in this task. The basic idea of Siamese network is that the two input image array share a series of convolutional and max-pooling layers. After the share network, the calculated two groups of latent variables are fed into constative loss layer to minimize the contrastive loss.

The constrastive loss is defined:

contrative_loss=label{true}\*dist(left, right) + (1-label{true})\*max( margin - dist(left,right), 0)

