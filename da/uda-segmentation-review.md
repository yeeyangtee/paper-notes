# Unsupervised Domain Adaptation in Semantic Segmentation: A Review

Review paper in 2020 for domain adaptation focusing on semantic segmentation applications. 

### Core problem formulation: 
1. deep learning (esp semantic segmentation) needs a lot of labelled data  
2. collecting and annotating is expensive, time consuming, error prone  
3. in many situations, we dont have sufficient training data for a certain task but there exists large amount of labelled data available for OTHER domains (similar to the one of interest) for certain reasons  
4. we want a way to utilize such 'other' data.

### Adaptation Spaces
DA aims to solve the problem of covariate shift (domain gap etc etc) between source and target datasets. There are a few 'locations' that we can address this:
- Input level, perform statistical matching at inputs using things like image-image translation
- Feature level, perform matching of network latent embedding, e.g. pass source and target through a same network, optimise the features to be similar
- Output level, somehow align on the segmentation output space. E.g. align the label statistics over the output segmentation map, some high level structure properties.
- Network level, ???


**Key points:**
- Adversarial learning
- generative based methods
- analysis of classifier discrepancies
- self teaching/ learning
- entropy minimisation
- curriculum learning
- multi-task learning

