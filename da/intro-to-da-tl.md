# Introduction to domain adaptation and transfer learning
A review paper on these 2 closely related topics. Main topics covered would be:
- Definition of domain
- Data shifts

Generally this review is very theoretical, focuses on low dimensional data with single value outputs. But the fundamentals should still be applicable to vision stuff.

The main idea of domain adaptation is... to train a classifier on a **source** dataset, and have it generalize to a **target** dataset without requiring the labels of the target dataset.

## Definition of 'domain'
A combination of input space X, output space Y and probability distribution p. Two domains are considered different if there are any differences in any of these 3 components.

*Transfer learning* is the general case whereby domains are allowed to differ in input space/ output space/ probability distribution, an example would be image caption generators that generalize from images to text. (input space is totally different)

*Domain adaptation* is defined as a more specific case whereby input and output spaces are consistent, only probability distributions change. 

## Common Data Shifts
These are based on Bayesian probability theory, and decompose the different types of data shifts between source and target domains.
### 1. Prior Shift
Difference in the output class distribution. Solution: ensure both domains are similary weighted by class. E.g. source population contains 90% male and 10% female while target population contains 90% female, 10% male.

### 2. Covariate Shift
The source/input distributions are different. This is typically caused by sampling bias.

### 3. Concept Shift
Posterior probabilities/ distributions are different.

### 4. General Shift 
Combination of the above 3.

## Key approaches to domain adaptation:
Only wrote some of the more applicable ones.
### 1. Importance Weighting
Essentially changing the percentage weight of the source domain to match target domain, then train model with source domain data.
At times the class distribution of target domain is unknown. So can also estimate the weights

### 2. Subspace mapping
source and target domain could exist in different subspaces. There could exist some sort of mapping between them, such as rotation, affine transformation, nonlinear transformations. In high dimensional applications such as vision... probably need a complex nonlinear transformation (conv-net). Traditional technique is to take principal components, then rotate source components to align with target components.

### 3. Finding domain invariant spaces
find a domain invariant space where a domain classifier cannot recognise from which domain a new sample is drawn from. Check out Domain Adversarial Neural Networks.

## Discussion pointers
- Need better understanding of the source of domain shifts. In traditional institutes, datasets can differ due to some 'batch' effects such as weather, time of day, lab conditions etc. Sharing or incorporating such info as metadata could help domain transfer.
- **Sequential adaptation**: Use a series of domain transfer instead of one large jump. E.g. adapt from Europe to asian hospitals, can do west to east europe, to middle east, then asia. Not necessarily using subspace mapping, each hop can be using a combination of techniques so its not a linear thing. But of course, there's the problem of error accumulation.



