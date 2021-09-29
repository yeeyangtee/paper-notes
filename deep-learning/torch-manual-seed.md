# torch.manual seed(3407) is all you need

Just a study (with a cool name) on the effect of random seed selection on Deep NN accuracy. The main experiement setup is to run a train-test evaluation over a large amount of random seeds, then record down the accuracy. 

Some limitations with this are that the models were not always trained to convergence due to resource constraints.  

## What does the seed affect in the experiments?
This wasn't made super clear but the following are the 2 main things, which is something usually treated as negligible!
- Initialisation of model parameters
- Composition of batches during training

## There are 2 main experiment setups in this paper:
### 1. Cifar 10
10,000 seeds were scanned, ResNet-9 from DAWN benchmark was used. From this setup, the best and worst accuracy had a 1.82% difference. That is very significant! Argument is that each year there are more than 10,000 submissions to CV conferences, hence that could be seen as an 'evolutionary' style selection of the authors that managed to find the best seeds.

### 2. Imagenet
Only 50 seeds were scanned due to the much longer training time on imagenet. Networks used were some resnets and SSL variations of those (some pretrained on other datasets). Here pretrained networks were used, so only the final classification layer is randomly initialized.

Difference of max and min accuracy was only 0.5%. However taking into consideration that only 50 seeds + competitiveness of CV work + very small randomness (init final layer), this is actually quite significant!

