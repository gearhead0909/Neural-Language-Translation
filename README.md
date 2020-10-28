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
The same can be downloaded form [Here](https://code.google.com/archive/p/word2vec/)

