# ONCE-FOR-ALL: TRAIN ONE NETWORK AND SPECIALIZE IT FOR EFFICIENT DEPLOYMENT

main claim here is to solve the efficient deployment problem: given varying deployment devices with varying compute ability, how to create a suitable network? previous methods do manual design of architectures or perform neural architecture search for each application - extremely long training times.

## Method
- Decouple train and search. During training, create a big once for all network. Optimise for sub-networks at the same time.
- During inference, select sub-networks depending on compute/memory constraints from the OFA network. Then just finetune the subnetwork. Since subnets were optimised during main training, it should have decent accuracy.
- Training method: progressive shrinking. Something like model pruning. First train the largest possible network, then shrink the model in all 4 modes (depth, width, resolution, kernelsize). The optimisation or finetuning of subnetworks is done by sampling from a 'network space'. As progressive shrinking occurs, we get more possible selections from the network space (smaller depths, widths etc).

results are dope, winning a few CVPR low power CV challenges. cool stuff.

[code](https://github.com/mit-han-lab/once-for-all)