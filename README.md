# Neural-Language-Translation
This project translates English language to Hindi language using Deep Neural Network.
To build the model for training, we used Seq2Seq Encoder-Decoder architecture.

Neural Machine Translation require a huge dataset to learn the pattern,
but due to system limitation we used a small dataset of English to Hindi translated sentences.

English sentences are used as input to the Encoder and Hindi sentences as Input and Target sequences of the Decoder.
LSTM based Encoder-Decoder model is built to train the Deep Neural Model.
This model can be used to translate any language to any desired language. 

Pre-processing of the sentences is performed on the text input to remove the extra unnecessary information.
The steps of pre-processing involves :-

1. Lower-Casing
2. Expand-Contractions
3. Removing Special Characters
4. Removing Numbers
5. Removing Extra Spaces

For Expansion of Contractions, we used Google-NewsVector-300 for precise expansion.
The same can be downloaded form [Here](https://code.google.com/archive/p/word2vec/).

After pre-processing of the text, we will add start and end tokens to prepare them for Decoder input/targets.
Since, Deep Neural Network can not work with words. We need to convert the words into vectors.

First, we will Tokenize the input sentences and convert the words into integers using Keras preprocessing library Tokenizer.
We dont want to filter start and end tokens so we dont add any filters while tokenizing the sentences.

Neural Network can only work with the input sentences of same length.
To make all the input sentences of the same length we will pad the sentences with zeros.
After padding all the squences, sequences are ready to fed into the Neural Network.

Then, we will make an Embedding Layer to convert every word to respective vector.
we used GLoVe pre-trained word dictionary to make an embedding layer.
Pre-trained word2vec dictionary can be downloaded from [Here](https://nlp.stanford.edu/projects/glove/).

To make Decoder targets, we will one-hot encode the Target sequence words.
Shape of one-hot targets will be :- (number of sentences, max length of output sequences, number of unique words in output sentences)

Then we manually make layers for Encoder-Decoder architecture.
Model will be defined with input and outputs.
The architecture of the model is shown below :-
