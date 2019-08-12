There is a major drawback to using GANs for generating discrete data, since backprop requires continuity in both neural network model
and training data. This limits its data generating ability in the area that requires discrete data, such as image segmentation, 
machine translation and caption generation. 

Boundary-seeking GANs avoids directly backpropagation by approximating a gradient for generator
training. This gradient resembles importance sampling, and is constructed based on KL divergence.
It can be used to train a generator of discrete data without relying on back-prop through the
generative process.

