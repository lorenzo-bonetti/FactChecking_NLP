
## Comments/summary
### Dataset preprocessing
We cleaned a bit the texts removing parentheses, punctuation and strange characters.

### Dataset conversion
We embedded each word of claims and evidences using glove embedding and we treated OOV using the neighbour strategy.

### Model definition
We defined 4 different models:

A bidirectional LSTM which takes as input a sentence and return the last hidden state as sentence encoding
A bidirectional LSTM which takes as input a sentence and return the average of all the hidden states as sentence encoding
A simple MultiLayer Perceptron which takes as input a sentence and returns the output of the fully connected layer as the encoding of the sentence
A BOV model which simply takes as input a sentence and returns the average of the glove embedding of all the words in the sentence
Training
In the training, first all the models are tested using the same merging strategy: average.

Then the best model is chosen and is tested with all the merging strategies.

In the end the best model is tested with the best strategy and with the cosine similarity concatenated to the input of the classifier.

The notebook we uploaded only shows results from the last run, since it was too long to run everything together.

### Evaluation
First we evaluated the results of the classifier looking only at the numbers of the pairs claim/evidence correctly classified.

Then we aggregated the pairs referring to the same claim and through a major voting we evaluated the quality of the classification in relation the claim.

### Credits
Lorenzo Bonetti

Giulio Fortini
