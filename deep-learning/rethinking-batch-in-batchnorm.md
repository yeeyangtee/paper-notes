# Rethinking Batch in BatchNorm

**Review** on batchnorm from Facebook AI, one of the two authors is justin johnson, an OG in modern CV.
Main idea of BN as we know it is to normalize data across a batch, and has been shown to improve training speed, provide regularisation. Pretty much every CNN model uses this.. This is a very comprehensive review, yet to finish reading..


## Key takeaways
- EMA might not be the best way to compute train-set stats! Consider PreciseBN when needed. EMA could perform poorly if batch size is too small or model is not converged.
- Be consistent with your choice of norm statistics across train and test. If you train with minibatch stats, test with minibatch stats. 


## EMA, Learning Training data statistics
- On learning training set statistics to be used at inference time: Using EMA might not be ideal as we have all assumed. Need an idea lambda value, too large lambda means slow convergence, too small means recent samples (random) will dominate the EMA stats. Also, at different training steps EMA might not give a sufficiently accurate result as it usually 'lags' behind the population mean. Large batch training is found to perform poorly for EMA. (They tested BS = 8k lol)
- Proposed PreciseBN which is supposedly a way to better compute statistics across the whole training set. Main idea is just record down multiple mini-batch statistics, then take an average to approximate the population stats. This is actually how it was done before EMA became popular.
- 