# DIVIDEMIX: LEARNING WITH NOISY LABELS AS SEMI-SUPERVISED LEARNING

Main idea is a combination of co-dividing training data and MixMatch semisupervised learning. They also use the idea of dividing up training data based on how 'noisy' the labels are, then incorporating this into MixMatch.
- Two networks are trained separately.
- Co-divide uses a gaussian mixture model to separate noisy and clean data, the data split is used to train the **other** network. This allows both networks to filter for different types of noise, and also to avoid confirmation bias during self training step.
- Mix Match is improved using label co-refinement and co-guessing. Need to read more on this
- Not sure about details of MixMatch

Codivide is done using loss modelling. The crossentropy loss is used as a scoring metric for how 'clean' the data is. GMM uses a thresholding to divide training data into clean and noisy based on the CE score.

There is an interesting addition of a confidence penalty on this loss modelling part, whereby a negative entropy term is added to the cross entropy loss/score. This forces the classification model to also maximise the entropy, which lets the loss terms become more evenly distributed, hence easier to model by GMM. This is only done during the warm up training phase i think.

[MixMatch](https://arxiv.org/abs/1905.02249) can be summarised by consistency regularisation (model should make same predictions on pertubed unlabelled data) and entropy minimisation (moidel should have confident predictions on unlabelled data) and also MixUp which enforces linear behaviour between unlabelled samples.

Improvements of co-refinement

Improvements of co-guessing

[code](https://github.com/LiJunnan1992/DivideMix)