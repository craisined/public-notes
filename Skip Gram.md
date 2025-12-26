#Coding
# Abstract

> \"No one is going to implement word2vec from scratch\" or sm 🤓
> commentary like that idk

This notebook provides a brief explanation and implementation of a Skip
Gram model, one of the two types of models word2vec refers to.

# Intuition

## Problem

Given a corpus C, map all tokens to a vector such that words with
similar semantics (similar probability of appearing within a context)
close to each other.

## Idea

**The idea of a skip gram model proceeds from these two observations:**

1.  Similar words should appear in similar contexts
2.  Similar words should appear together

The intuition behind the Skip Gram model is to map a target token to all
the words appearing in a context window around it.

> The MIMS major **Quentin** is a saber fencer.

In this case the target token **Quentin** should map to all the other
tokens in the window. As such the target token should have similar
mappings to words such as MIMS, saber, and fencer.

Skip Gram treats each vector representation of a token as a set of
weights, and uses a linear-linear-softmax model to optimize them. At the
end, the first set of weights are a list of $n$ vectors that map a token
to a prediction of output tokens - solving the initial mapping problem.

# Code & Detailed Implementation

## Preproccessing

Tokenize all the words, and build training pairs using words in a
context window:

``` python
import numpy as np

class Preproccess:

  @staticmethod
  def tokenize(text):

    """Returns a list of lowercase tokens"""

    return "".join([t for t in text.lower().replace("\n", " ") if t.isalpha() or t == " "]).split(" ")

  @staticmethod
  def build_vocab(tokens, min_count=1):

    """Create an id to word and a word to id mapping"""

    token_counts = {}
    for token in tokens:
      if token not in token_counts:
        token_counts[token] = 0
      token_counts[token] += 1

    sorted_tokens = sorted(token_counts.items(), key=lambda t:t[1], reverse=True) # Sort tokens by frequency
    vocab = {}
    id_to_word = [0] * len(sorted_tokens)
    for i in range(len(sorted_tokens)):
      token, count = sorted_tokens[i]
      if count < min_count:
        break
      id_to_word[i] = token
      vocab[token] = i

    return vocab, id_to_word

  @staticmethod
  def build_pairs(tokens, vocab, window_size=5):

    """Generate training pairs"""

    pairs = []
    token_len = len(tokens)

    for center in range(token_len):
      tokens_before = tokens[max(0, center-window_size):center]
      tokens_after = tokens[(center + 1):min(token_len, center + 1 + window_size)]
      context_tokens = tokens_before + tokens_after
      for context in context_tokens:
        if tokens[center] in vocab and context in vocab:
          pairs.append((tokens[center], context))

    return pairs

  @staticmethod
  def build_neg_sample(word, context, vocab, samples=5):

    """Build negative samples"""

    neg_samples = []
    neg_words = [vocab[w] for w in vocab if (w != word) and (w != context)]
    neg_samples = np.random.choice(neg_words, size=samples, replace=False)
```

## Build Model

-   3 layers used as an optimizer:
    -   $L_1 = XW_1$
    -   $S = W_2 L_1$
    -   $P = \text{softmax(S)}$
-   Loss function: $-\sum \log(P_{\text{context}} | P_{\text{target}})$
-   Negative sampling used to speed up training, compare and update
    against \~20 negative vocab terms instead of updating all weights

``` python
class Word2Vec:

  def __init__(self, vocab_size, embedding_dim=100):

    """Initialize weights"""

    self.vocab_size = vocab_size
    self.embedding_dim = embedding_dim
    self.W1 = np.random.normal(0, 0.1, (vocab_size, embedding_dim)) # First layer - word encoding
    self.w2 = np.random.normal(0, 0.1, (embedding_dim, vocab_size)) # Second layer - context encoding

  def sigmoid(self, x):

    """Numerically stable sigmoid"""

    x = np.clip(x, -500, 500)
    return 1 / (1 + np.exp(-x))

  def cross_entropy_loss(self, probability):

    """Cross entropy loss function"""

    return -np.log(probability + 1e-10) # 1e-10 added for numerical stability

  def neg_sample_train(self, center_token, context_token, negative_tokens, learning_rate=0.01):

    """Negative sampling training for a single training pair"""

    total_loss = 0
    total_W1_gradient = 0

    # Forward prop for positive case
    center_embedding = self.W1[center_token, :] # L₁ = XW₁
    context_vector = self.W2[:, context_token]
    score = np.dot(center_embedding, context_vector) #L₂ = L₁W₂, but only for the context token vector
    sigmoid_score = self.sigmoid(score)
    loss = self.cross_entropy_loss(sigmoid_score)
    total_loss += loss

    # Backward prop for positive case
    score_gradient = 1 - sigmoid_score # ∂L/∂S
    W2_gradient = center_embedding * score_gradient # ∂L/∂W₂ = ∂L/∂S * ∂S/∂W₂ = XW₁ * ∂L/∂S
    W1_gradient = context_vector * score_gradient # ∂L/∂W₁ = ∂L/∂S * ∂S/∂W₁ = W₂ * ∂L/∂S

    # Update weights
    self.W2[:, context_token] -= learning_rate * W2_gradient
    total_W1_gradient += learning_rate * W1_gradient

    for neg_token in negative_tokens:

      # Forward prop for negative case
      neg_vector = self.W2[:, neg_token]
      neg_score = np.dot(center_embedding, neg_vector)
      neg_sigmoid_score = self.sigmoid(neg_score)
      neg_loss = -np.log(1 - neg_sigmoid_score)
      total_loss += neg_loss

      # Backward prop for negative case
      neg_score_gradient = sigmoid_score
      neg_W2_gradient = center_embedding * neg_score_gradient
      neg_W1_gradient = context_vector * neg_score_gradient

      # Update weights
      self.W2[:, neg_token] -= learning_rate * neg_W2_gradient
      total_W1_gradient -= learning_rate * neg_W1_gradient

    # Update W1
    total_W1_gradient = np.clip(total_W1_gradient, -1, 1)
    self.W1[center_token, :] += total_W1_gradient

    return total_loss

  def find_similar(self, token):

    """Use cos similarity to find similar words"""

    word_vec = self.W1[token, :]
    similar = []
    for i in range(self.vocab_size):
      if i != token:
        other_vec = self.W1[i, :]
        norm_word = np.linalg.norm(word_vec)
        norm_other = np.linalg.norm(other_vec)
        if norm_word > 0 and norm_other > 0:
            cosine_sim = np.dot(word_vec, other_vec) / (norm_word * norm_other)
        else:
            cosine_sim = 0
        similar.append((cosine_sim, i))
    similar.sort(key=lambda x:x[0], reverse=True)
    return [word[1] for word in similar]
```

## Run Model

``` python
def epoch(model, pairs, vocab):
  loss = 0
  pair_len = len(pairs)
  done = 0
  for word, context in pairs:
    neg_samples = Preproccess.build_neg_sample(word, context, vocab, samples=5)
    loss += model.neg_sample_train(word, context, neg_samples)
    done += 1
    if ((100 * done) / pair_len) // 1 > ((100 * done - 100) / pair_len) // 1:
      print("_", end="")
  return loss

with open("corpus.txt") as corpus_file:
  CORPUS = corpus_file.read()

EPOCHS = 100
tokens = Preproccess.tokenize(CORPUS)
vocab, id_to_token = Preproccess.build_vocab(tokens, min_count=3)
print("~VOCAB LEN~:", len(vocab))
pairs = Preproccess.build_pairs(tokens, vocab, window_size=5)
model = Word2Vec(len(id_to_token), embedding_dim=100)
print("~STARTING TRAINING~")
for i in range(EPOCHS):
  print(f"Epoch {i}: {epoch(model, pairs, vocab) / len(id_to_token)}")
print("~FINISHED TRAINING~")
```
# Notes (Pedantic Commentary Defense :P)

1.  I use the term \"similar\" and \"related\" in reference to words,
    which implies some sort of meaning is encoded. However in practice
    word2vec is just looking for words with high probabilities of being
    in similar contexts, which happens to correlate to \"meaning\"
    decently well.
2.  CBOW shares a very similar intuition to Skip Gram, the only
    difference is which way you map a target token to context tokens.
3.  Of course, a good deal of mathamatical pain can be shaved off this
    excercise by using Tensorflow (here is a
    [Colab](https://colab.research.google.com/github/tensorflow/text/blob/master/docs/tutorials/word2vec.ipynb#scrollTo=iLKwNAczHsKg)
    from Tensorflow that does it) - but this is done from scratch so the
    inner workings of word2vec can be more easily seen.
4.  Results are (very) subpar with a small corpus size, and this isn\'t
    optimized for GPUs sooo\... at least the error goes down!

# Sources

1.  <https://en.wikipedia.org/wiki/Word2vec>
2.  <https://arxiv.org/abs/1301.3781> (worth a read - not a long paper
    and def on the less math intensive side of things)
3.  <https://ahammadnafiz.github.io/posts/Word2Vec-From-Scratch-A-Complete-Mathematical-and-Implementation-Guide/#implementation>
