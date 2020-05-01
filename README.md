# simple-seq2seq-chatbot
**Introduction**
---
This is our final project for CSE691 MIDL 20spring. We build a simple seq2seq chatbot based on tensorflow 2, using the [cornell movie dialog corpus](https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html). Our code is basically refered to the [keras example](https://blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html) and the [tensorflow tutorial](https://www.tensorflow.org/tutorials/text/nmt_with_attention). We have implemented 3 different version, the basic lstm model, basic gru model and gru model with attention mechanism and compared their performance.   
In order to earn extra point, we also implement a simple Chinese-to-English translator using our model. The corpus comes from [here](https://github.com/pjgao/seq2seq_keras) 

**Enviroment**
---
-  Python 3.7
-  Tensorlow 2.1
-  Numpy

**Usage of Our Code**
---
-  **If you want to use our chatbot**:   
    1. **Run 'datapreprocessing'**: You can define the length of your own training data. We only use some short sentences(2 to 8 words) and a small vocabulary size(2500 words) to test our code.  
    2. **Run 'gru_training_model' (or 'lstm_training_model') to train the model**: If you modified the training data in 'datapreprocessing', some details in the training model file should also be adjusted. Also, our model is a prelimilary version, you can modify it by yourself to improve the performance. 
    3. **Run 'bot_gru'(or 'bot_lstm')**: If you modified the training model, don't forget to modify code at here. Again, we use the greedy algorithm to predict the answer of the bot at here. You can improve the output by using beam search decoder.
-  **If you want to use our translator**: We highly recommand you don't use it directly because we complete that code in a very short time and it is a character-level model(because it's easy to train). It doesn't generate a qualified translation in general scenario. it just performs good in training data. If you want to build a translator, you should use the word-level model, some places of our code should be modified.  

**Performance**
---
-  **result of lstm model**   

![image text](https://github.com/milinzhang/simple-seq2seq-chatbot/blob/master/image/bot_lstm.png)  

-  **result of gru model**  

![image text](https://github.com/milinzhang/simple-seq2seq-chatbot/blob/master/image/bot_gru.png)

-  **result of attention model**  


-  **result of translator**

![image text](https://github.com/milinzhang/simple-seq2seq-chatbot/blob/master/image/translator.png)  

**Inprovement**
---
-  1.train on different dataset  
    We use a small dataset only containing short sentences in cornell movie dialog corpus. Training model on a larger dataset is beneficial to improve the performance of the bot. Also, the cornell movie dialog contains lots of dramatic conversations since playwriters need to promote the plot. Using other corpus can make the bot more realistic.  

-  2.non-greedy prediction  
    In our code, we use a argmax function to generate the most potential word at each timestep during the prediction. But the greedy prediction may be not the optimal one. So, the performance can be improved by making use of beam search algorithm.  
    
-  3.sparse-categorical-crossentropy  
    In the gru and lstm model, we use categorical crossentropy to train, which expect labels to be one-hot encoding. But with the vocabulary size increased, the memory requirement will be enormous. In order to avoid the oom issue we only use a small batchsize and this will slow down the training. You can use sparse categorical crossentropy to solve this problem, just like what we do in the attention model.

-  4.word-level translator  
    In our code we use a character-level model and its performance is limited. Use a word-level model is more general.
