# PCB Component Detection Using Computer Vision for Hardware Assurance

## Summary | Problem statement
- Want to do PCB detection, ML techniques are higher accuracy but are not so good because need a lot of data, low explanability
- They propose to use CV methods and compare (?) or integrate with ML techniques


## main contributions 
- Apply CV techniques using semantic data (pixel-wise label?) while previous works mainly do bounding box information (not sure if true)


## Method summary
### Feature Extraction
- Use colour, shape, texture to extract features.
- Colour: feature extraction method are in terms of the colour space, which they use RGB, HSV, Lab. Not sure how to extract after that.. probably some sort of thresholding.
- Shape: DoH for blob detection, corner subpixel detection, and edge detection
- Texture: Gabor filter, gray level co-occurence matrix, local binary patterns.

### Feature processing
- After grabbing all the features, e.g. for RGB it seems to be just RGB image map, pass to random forest.
- Use RF to weight the importance of each feature (why?), to get the features that have most weightage to classification task.
- What is the final objective that the classifiers optimize to? Is it the pixel-wise ground truths, then the classifier is doing pixel wise classification?