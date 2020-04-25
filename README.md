# simple-seq2seq-chatbot
**Introduction**
---
This is our final project for CSE691 MIDL 20spring. We build a simple seq2seq chatbot based on tensorflow 2, using the [cornell movie dialog corpus](https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html). Our code is basically refered to the [keras example](https://blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html) and the [tensorflow tutorial](https://www.tensorflow.org/tutorials/text/nmt_with_attention). 

**Enviroment**
---
-  Python 3.7
-  Tensorlow 2.1
-  Numpy

**Usage of Our Code**
---
-  If you want to chat with our bot: run 'bot_gru'(or 'bot_lstm')
-  If you want to train your own bot:   
    1. Run 'datapreprocessing': You can define the length of your own training data. We only use some short sentences(2 to 8 words) and a small vocabulary size(2500 words) to test our code.  
    2. Run 'gru_training_model' (or 'lstm_training_model') to train the model.  
    3. Run 'bot_gru'(or 'bot_lstm')
    
**Performance**
