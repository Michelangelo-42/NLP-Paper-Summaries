This paper proposes a neural probabilistic language model which fights &quot;the curse of dimensionality&quot; by learning a distributed representation for words.  In contrast to the classical trigram model, this paper (1) associates a distributed word feature vector with each word in the vocabulary, (2) expresses the joint probability function for a word sequence in terms of those feature vectors, and (3) learns word feature vectors and (parameters of) the joint probability function at the same time. To fight the curse of dimensionality, the model&#39;s ability to generalize comes from the belief that &quot;similar&quot; words have similar feature vectors. Also, the &quot;smooth&quot; probability function plays a role. However, the difficulty is &quot;shifted elsewhere&quot; (more computation is needed).

Based on previous work, neural networks are used to model probability functions of high-dimensional discrete distributions for words. As a high-level description, the applied neural network with 1 (2?) hidden layer takes the following as parameters: matrix C of feature vectors, biases b and d, weights W, U, H (for different corresponding layers or layer-layer&#39;s). Although the number of parameters is large, it fortunately scales linearly with the size of vocabulary and order n. In other words, the training of the model is &quot;expensive but feasible&quot;. Moreover, parallel implementation such as data-parallel and parameter-parallel processing with careful synchronization and parameter sharing mechanisms helps accelerate the computation (especially, activations of the output layer).

Brown corpus (w/ many examples) and Associated Press News (1995-1996, w/ many words) are used to perform experiments.  The proposed model shows significantly better &quot;perplexities&quot; (geometric average of one over conditional probabilities) than the trigram model. It is also observed that direct input-to-output connection might be unnecessary for good generalization and that mixture of two competing models reduces perplexity. In the part of future work, the authors discuss a new viewpoint of the model as an energy minimization model, representation of conditional probability with a tree structure, introduction of a-priori knowledge and so on.