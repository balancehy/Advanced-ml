# Handwriting formation analysis

Use probabilistic graphical model to analyze handwriting formations. Constructed different graph structures and evaluated their likelihood based on dataset. Found the most and least probable formation using ancestral sampling approach.

Consider two letter "th" in this study. Six features of this pattern are defined as followings. Each feature has several values.
- ![](https://latex.codecogs.com/gif.latex?x_%7B1%7D) Height relation of t to h
  - t shorter than h
  - t even with h 
  - t taller than h
  - no pattern
- ![img](https://latex.codecogs.com/gif.latex?x_%7B2%7D) Shape of loop of h
  - retraced
  - curved right side and straight left side
  - curved left side and straight right side
  - both sides curved
  - no fixed pattern
- ![img](https://latex.codecogs.com/gif.latex?x_%7B3%7D) Shape of arch of h
  - Round arch
  - pointed
  - no set pattern
- ![img](https://latex.codecogs.com/gif.latex?x_%7B4%7D) Height of cross on t staff
  - Upper half of staff
  - lower half of staff
  - above staff
  - no fixed pattern
- ![img](https://latex.codecogs.com/gif.latex?x_%7B5%7D) Baseline of h
  - slanting upwards
  - slanting downward
  - baseline even
  - no set pattern
- ![img](https://latex.codecogs.com/gif.latex?x_%7B6%7D) Shape of t
  - tented
  - single stroke 
  - looped
  - closed
  - mixture of shapes

For example, the first sample can be expressed as ![](https://latex.codecogs.com/gif.latex?x_%7B1%7D%5E%7B1%7D%2Cx_%7B2%7D%5E%7B0%7D%2Cx_%7B3%7D%5E%7B0%7D%2Cx_%7B4%7D%5E%7B3%7D%2Cx_%7B5%7D%5E%7B0%7D%2Cx_%7B6%7D%5E%7B1%7D). The second sample ![](https://latex.codecogs.com/gif.latex?x_%7B1%7D%5E%7B1%7D%2Cx_%7B2%7D%5E%7B1%7D%2Cx_%7B3%7D%5E%7B0%7D%2Cx_%7B4%7D%5E%7B1%7D%2Cx_%7B5%7D%5E%7B0%7D%2Cx_%7B6%7D%5E%7B2%7D) 

![](figures/th_1.png)           ![](figures/th_2.png)

       [1]                               [2]
        
We are given all marginal probability of each feature for its each value, and some conditional probability indicating the dependency between twe features. Then we can construct Bayesian network to do inference and query task.
