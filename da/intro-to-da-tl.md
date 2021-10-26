# Introduction to domain adaptation and transfer learning
A review paper on these 2 closely related topics. Main topics covered would be:
- Definition of domain
- Data shifts
- 

The main idea of domain adaptation is... to train a classifier on a **source** dataset, and have it generalize to a **target** dataset without requiring the labels of the target dataset.

## Definition of 'domain'
A combination of input space X, output space Y and probability distribution p. Two domains are considered different if there are any differences in any of these 3 components.

*Transfer learning* is the general case whereby domains are allowed to differ in input space/ output space/ probability distribution, an example would be image caption generators that generalize from images to text. (input space is totally different)

*Domain adaptation* is defined as a more specific case whereby input and output spaces are consistent, only probability distributions change.

## Common Data Shifts
These are based on Bayesian probability theory, and decompose the different types of data shifts between source and target domains.
### 1. Prior Shift
Difference in the output class distribution. Solution: ensure both domains are similary weighted by class.

### 2. Covariate Shift
The source/input distributions are different. This is typically caused by sampling bias.

### 3. Concept Shift
Posterior probabilities/ distributions are different.

### 4. General Shift 
Combination of the above 3.

## Key approaches to domain adaptation:
### 1. Importance Weighting

### 2. Subspace mapping
### 3. Finding domain invariant spaces
### 4. Feature augmentation
### 5. Minimax estimators
### 6. Robust algorithms
