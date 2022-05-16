# A generalist agent

## Main ideas/ summary
- Create a multi-modal, multi-task AI.
- Train one model with common weights to do variation of tasks such as play games, image captioning, stack blocks.

## Concrete stuff
- Transformer sequence model, essentially we need to convert any task into some sort of sequence, then model can predict the upcoming tokens.
-  Tokenisation of data follows previously established methods, e.g. text is encoded with SentencePiece, image using ViT(16x16 patches), etc.
-  Relatively small model size used to be suited for real-time deplayment (1.2 B parameters)

### Important text, directly quoted
1. We hypothesize that such an agent can be obtained through scaling data, compute and model parameters, continually broadening the training distribution while maintaining performance, towards covering any task, behavior and embodiment of interest.
2. In this setting, *natural language can act as a common grounding across otherwise incompatible embodiments*, unlocking combinatorial generalization to new behaviors. 
