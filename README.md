# MI-LSTM

<h2> Deep Learning project for predicting close stock prices using MI-LSTM </h2>

<img src="https://github.com/yuvalmargules/MI-LSTM/blob/master/MI-Cell.png" width=600>

<p> MI-LSTM is an LSTM based model which takes into consideration stocks from positive correlated companies, negative correlated companies, and the index it belongs to.
In order to calculate those variables within the LSTM cell, we use Attention Mechanism with learning weights of which we can trace the weights during the process and get insights about the market's status. </p>

<img src="https://github.com/yuvalmargules/MI-LSTM/blob/master/MI-LSTM.jpg" width=600>

<div>
  In the picture above we see the whole process of the model we built. Firstly, for window of size T, we define:
  <ul>
    <li> Self: The company we want to predict </li>
    <li> Pos: N positive correlated comapnies </li>
    <li> Neg: N negative correlated comapnies </li>
    <li> Idx: The index(e.g S&P500) </li>
  </ul>
  All windows of size T belong to the inputs above will go first through the LSTMLayer.class which shared weights(only one LSTM layer, not an LSTM for each one). Then, it will go through the MI_Cell.class where the Attention is applied. After that, we get the outputs for each day in the window and we apply Dual Stage Attention AttentionLayer.class for getting the desired output of size (1, hidden_size). At last, we go through 2 fully connected neural networks using Tanh as an activation function to get the final prediction.
</div>

<div>
Example from results:
  <img width="1034" alt="Corr" src="https://user-images.githubusercontent.com/63664364/111044143-5fd4da80-844f-11eb-89b6-f6959c25203c.png" width=400>
  <img width="1283" alt="Res" src="https://user-images.githubusercontent.com/63664364/111044156-67947f00-844f-11eb-9047-f28ae2afa090.png" width=500>

</div>

<div>
  This project implements the model suggested in this paper http://proceedings.mlr.press/v95/li18c/li18c.pdf
</div>
