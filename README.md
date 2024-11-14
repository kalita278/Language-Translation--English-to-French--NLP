# Language-Translation--English-to-French--NLP

## Problem Statement:
To Build a Neural Machine Translation (NMT) model which can translate language from English to French.

## Tokenizing and Vectorizing the Text:
Here we are building a Character level translation tool. So each token of our Input text shall be a character and each token of the target text will be a French character. We therefore convert the input data into a three dimensional array. The first dimension consists of number of English to French pairs, the second dimension consists of the length of each sentence. ( Here, we are taking the length of each sentence to be the length of the longest sentence in each of these languages, and for sentences whose lengths are smaller than the highest length, we are padding them with the ' ' token or a blank space token). The third dimension has a length equal to number of unique characters in that particular language, as this vector is a one-hot encoded vector for English and French alphabets.

## Encoder and Decoder Architecture
The Architecture has two units, the Encoder LSTM blocks and the Decoder LSTM blocks.

Theoretically in a Sequence to Sequence architecture, the output of the Decoder at one time step is used as an input for the next decoder time step. But during training, we are using the Ground Truth value for the input to the next decoder time step, so that our model learns better. This is called Teacher forcing.

We shall however change this in the inference or the testing stage, where we shall use the more traditional method of using the output of previous decoder time step as the current input to predict the output character.

<p align="center">
    <img width="500" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQAGfe-CAf9WfbsHO76idzWsTBVJosbbZD0jg&s" alt="RAG">
</p>
