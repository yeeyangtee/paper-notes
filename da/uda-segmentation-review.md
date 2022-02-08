# Unsupervised Domain Adaptation in Semantic Segmentation: A Review

Review paper in 2020 for domain adaptation focusing on semantic segmentation applications. 

### Core problem formulation: 
1. deep learning (esp semantic segmentation) needs a lot of labelled data  
2. collecting and annotating is expensive, time consuming, error prone  
3. in many situations, we dont have sufficient training data for a certain task but there exists large amount of labelled data available for OTHER domains (similar to the one of interest) for certain reasons  
4. we want a way to utilize such 'other' data.

### Adaptation Spaces
DA aims to solve the problem of covariate shift (domain gap etc etc) between source and target datasets. There are a few 'locations' or 'adaptation spaces' that we can address this:
- Input level, perform statistical matching at inputs using things like image-image translation. Quite unique from the following spaces because it happens 'off' the training task.
- Feature level, perform matching or alignment of network latent embedding, e.g. pass source and target through a same network, optimise the features to be similar. This has worked well for classification task domain adaptation. BUT, for segmentation, the feature space is much more complicated as it contains structure and semantic information. (LOW+HIGH level)
- Output level, somehow align on the segmentation output space or even at the last few layer outputs of the network. E.g. align the label statistics over the output segmentation map, some high level structure properties.
- AdHoc Network level, implement alignment at various levels of the segmentation network, essentially a general form of the feature level.

**Key points:**
- Adversarial learning: produce data with similar statistical distribution
- generative based methods: perform translation with generator networks between domain at the input side.
- analysis of classifier discrepancies: capture different target representations using multiple classifiers on top of an encoder. Perform aligment on those.
- self teaching/ learning: use pseudo label kind of deal + confidence measure to guide the training.
- entropy minimisation: minimise entropy of target output probability maps, this reduces overconfidence.
- curriculum learning: learn easy tasks such as...global label distributions, then train segmentation network (harder task) following these properties,
- multi-task learning:??



