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
  All windows of size T belong to the inputs above will go first through the LSTMLayer.class which shared weights(only one LSTM layer, not an LSTM for each one). Then, it will go through the MI_LSTM_Cell.class where the Attention is applied. After that, we get the outputs for each day in the window and we apply Dual Stage Attention for getting the desired output of size (1, hidden_size). At last, we go through 2 fully connected neural networks using Tanh as an activation function to get the final prediction.
  </div>

