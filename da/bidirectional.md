# Bidirectional Learning for Domain Adaptation of Semantic Segmentation

## Contributions:
- novel biredctional learning framework for domain adaptation of segmentation
- self supervised learning algo to learn a better segmentation adaptation model

## Problem formulation:
standard stuff.
- segmentation task, difficult and expensive to get pixel level labels.
- CNN allow us to generate training data
- However, domain mismatch between real and synthetic data causes poor performance

## Key idea:
- bidirection learning: two modules trained in two directions, translation to segmentation and segment to translation.
- 'close loop learning' similar to cyclegan, key thing is how to design objective functions for both models to have feedback to each other.
- 


[code](https://github.com/liyunsheng13/BDL)