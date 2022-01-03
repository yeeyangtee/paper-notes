# Self-supervised learning: The dark matter of intelligence

## Main points and overview
- self supervised learning (SSL) is how we as humans excel in certain tasks such as driving and recognising objects, we learn from our background knowledge of the world.
- self supervising because there are signals from the data itself, use underlying structures in the data. General technique is to make the model predict unobserved or hidde parts o the input using the observed data.
- Easier for NLP (TEXT) compared to vision for the following reasons:
  - difficult to represent uncertainty of prediction for images than words. 
  - Finite number of words (vocabulary), but infinite number of images (combination of pixels * width * height of image)
  - Great example: if missing word is lion or cheetah, learning system can give probability to all possible words in vocab, and high probability to words representing large cats. If missing frame in a video, no way this can be done.
  
## Unified view of self supervised methods
Energy based functions are a way to view SSL methods. Essentially:
- SSL model will take in two inputs x and y and output a value which is 'energy'. 
- The energy value tells us how compatible the two inputs are (low value = compatible, vice versa.)
- Easy: show examples of x and y that are compatible, train to output low energy (data augment one image two ways)
- Difficult: ensure that for a particular input x, the y that are incompatible give higher energy than y that are more compatible. (relative energy levels to be accurate.)





