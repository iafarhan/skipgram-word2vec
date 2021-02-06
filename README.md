# skipgram-word2vec
Iteration based method to learn Word Vectors. Word2vec is a method whose parameters are word vectors.
#### Algorithm : Skipgram
Given a center word model generates the surrounding words. Steps are as follow
* We generate our one hot input vector 
* We get our embedded word vector for the center word
* Generate a score vector.
* Turn the score vector into probabilities using Softmax
* We desire our probability vector generated to match the true probabilities

As we are summing over the whole vocabulary in softmax and as our vocabulary size is huge this is inefficent to compute. so we use **Negative Samping** for optimization purposes.
For every training step, instead of looping over the entire vocabulary, we can just sample several negative examples
So now our objective is modified as negative sampling is optimizing a different objective. Briefly, Now we also want to know if a pair came from corpus data or not. the updated objective is defined in word2vec script.

Just to mention we could achieve the optimization by using Heirarchical softmax in place of Negative samping.
We train it for 40000 iteration. it takes about two hours to train.

