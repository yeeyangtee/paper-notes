# Logo Classification and Data Augmentation Techniques for PCB Assurance and Counterfeit Detection

## Summary | Problem statement
- PCB assurance has a lack of representative dataset for classification and detection tasks.
- PCB have low inter-class variance where different logos are similar to one another in terms of grayscale, simple backgruond, limited features.
- PCB logo has high intra-class variance, i.e. the same logo could look very different due to difference in shape, scale, imaging method, printing technique?


## Main contributions
- PCB logo augmentation techniques
- A dataset of logo based on these techniques for PCB assurance
- Do some initial experiments on PCB classification with some methods (Random forest, CNN etc)

## Method summary
1. Acquire variants of logo from online dataset (FICS-PCB Dataset), or scrape from internet.
2. Do some preprocessing and augmentation, including: pad to square aspect ratio, fill in texture around logo using mean and variance estimations, random rotation (+-20 degrees with 90 degree intervals), random zooming +-50%, shear transformations of 20%, median blurring.
3. 

