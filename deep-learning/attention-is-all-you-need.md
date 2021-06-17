# Attention is all you need

The OG transformers paper from bigbrain Googlers. Created for language tasks (in paper tested on machine translation) but making waves in many many other areas today (2021).

Introduces SELF-ATTENTION. Somewhat a build up from [attention](https://arxiv.org/abs/1409.0473) idea from even earlier on.

Good blog posts to read:
- [Super intuitive](https://jalammar.github.io/illustrated-transformer/)
- [Another blog](https://towardsdatascience.com/illustrated-self-attention-2d627e33b20a)

Main idea:
- Self attention is basically computing the relationship between each input word and every other input word in the sequence.
- Use key-query-value concept to do this. to get scores for word 1, query of word 1 is multiplied with key of all words. Take softmax to get the scores, which is a 'relation' between word 1 and each other input word. Scores are multiplied with each words' value vector. Sum up to get the output of the self-attention module. Repeat for each word using matrices. Pic below from [blog 1](https://jalammar.github.io/illustrated-transformer/) summarises nicely.
![](https://jalammar.github.io/images/t/self-attention-output.png)
- key-query-value vectors are obtained by multiplying input vectors with a K,Q,V matrix, which is learnt during training.

Other concepts:
- Multi-headed attention, essentially have multiple copies of this self-attention module. At the end you get 8 (however many heads) outputs for each word. Use normal FC layer to condense back to 1 output vector per input at the end.
- Positional embeddings to keep info about position of words.
- Residual connections within self attention module
- Not clear how decoder part works exactly. oops