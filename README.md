# Neural-Language-Translation
This project translates English language to Hindi language using Deep Neural Network.<br />
To build the model for training, we used Seq2Seq Encoder-Decoder architecture.<br /><br />

Neural Machine Translation require a huge dataset to learn the pattern,<br />
but due to system limitation we used a small dataset of English to Hindi translated sentences.<br /><br />

English sentences are used as input to the Encoder and Hindi sentences as Input and Target sequences of the Decoder.<br />
LSTM based Encoder-Decoder model is built to train the Deep Neural Model.<br />
This model can be used to translate any language to any desired language. <br /><br />

Pre-processing of the sentences is performed on the text input to remove the extra unnecessary information.<br />
The steps of pre-processing involves :-<br /><br />

1. Lower-Casing<br />
2. Expand-Contractions<br />
3. Removing Special Characters<br />
4. Removing Numbers<br />
5. Removing Extra Spaces<br /><br />

For Expansion of Contractions, we used Google-NewsVector-300 for precise expansion.<br />
The same can be downloaded form [Here](https://code.google.com/archive/p/word2vec/).<br /><br />

After pre-processing of the text, we will add start and end tokens to prepare them for Decoder input/targets.<br />
Since, Deep Neural Network can not work with words. We need to convert the words into vectors.<br /><br />

First, we will Tokenize the input sentences and convert the words into integers using Keras preprocessing library Tokenizer.<br />
We dont want to filter start and end tokens so we dont add any filters while tokenizing the sentences.<br /><br />

Neural Network can only work with the input sentences of same length.<br />
To make all the input sentences of the same length we will pad the sentences with zeros.<br />
After padding all the squences, sequences are ready to fed into the Neural Network.<br /><br />

Then, we will make an Embedding Layer to convert every word to respective vector.<br />
we used GLoVe pre-trained word dictionary to make an embedding layer.<br />
Pre-trained word2vec dictionary can be downloaded from [Here](https://nlp.stanford.edu/projects/glove/).<br /><br />

To make Decoder targets, we will one-hot encode the Target sequence words.<br />
Shape of one-hot targets will be :- (number of sentences, max length of output sequences, number of unique words in output sentences)<br /><br />

Then we manually make layers for Encoder-Decoder architecture.<br />
Model will be defined with input and outputs.<br />
The architecture of the model is shown below :-<br /><br />
<img src="https://github.com/gearhead0909/Neural-Language-Translation/blob/master/Model%20Training.png" alt="alt text" width="500" height="300"><br /><br />

The model did not achieve a very good validation accuracy because of limited system and small dataset.<br />
The performance of the model is shown below :-<br /><br />

Training and Validation Accuracy of the model is shown below :-<br />
<img src="https://github.com/gearhead0909/Neural-Language-Translation/blob/master/Accuracy.png" alt="alt text" width="500" height="300"><br />

Training and Validation Loss of the model is shown below :-<br />
<img src="https://github.com/gearhead0909/Neural-Language-Translation/blob/master/Loss.png" alt="alt text" width="500" height="300"><br />

After Training, we need to make a model to predict the target sequences for the test sequences.<br />
Architecture of the model for prediction is shown below :-<br /><br />
<img src="https://github.com/gearhead0909/Neural-Language-Translation/blob/master/Model%20Prediction.png" alt="alt text" width="500" height="300"><br /><br />

Our project successfully translated English language to Hindi Language.<br />
This model can further be improved with better system and dataset to train.
