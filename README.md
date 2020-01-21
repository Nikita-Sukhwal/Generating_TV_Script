# Generating_TV_Script

### Introduction
In this project, generated own Seinfeld TV scripts using RNNs. Used a Seinfeld dataset of scripts from 9 seasons. The Neural Network built generated a new, "fake" TV script.

### Getting the project files
The project files can be found on public GitHub repo of Udacity, in the project-tv-script-generation folder. The files can be downloaded from there, also, the repository can be cloned to computer using:
> git clone https://github.com/udacity/deep-learning-v2-pytorch.git

### Steps followed
- Getting the data
- Exploring the data
- Data Pre-processing
  - Lookup Table
    To create a word embedding, firstly it's needed to transform the words to ids. In this function, two dictionaries are created:
    * Dictionary to go from the words to an id: vocab_to_int
    * Dictionary to go from the id to word: int_to_vocab
   - Tokenize Punctuation
     Creating a dictionary for the following symbols where the symbol is the key and value is the token:
     * Period ( . )
     * Comma ( , )
     * Quotation Mark ( " )
     * Semicolon ( ; )
     * Exclamation mark ( ! )
     * Question mark ( ? )
     * Left Parentheses ( ( )
     * Right Parentheses ( ) )
     * Dash ( - )
     * Return ( \n )
     <br>This dictionary will be used to tokenize the symbols and add the delimiter (space) around it. 
- Building Neural Network
  Building the components necessary to build an RNN by implementing the RNN Module and forward and backpropagation functions.    
  * Model Layers
  define model layers
  > self.embedding = nn.Embedding(vocab_size, embedding_dim)<br> 
  > self.lstm = nn.LSTM(embedding_dim, hidden_dim, n_layers, dropout=dropout, batch_first=True)<br>
  > self.fc = nn.Linear(hidden_dim, output_size)
- Training Neural Network
- Training Parameters
  - Number of Epochs: num_epochs = 20
  - Learning Rate: learning_rate = 0.003 
  - Model parameters
  - Vocab size: vocab_size = len(vocab_to_int)
  - Output size: output_size = vocab_size
  - Embedding Dimension: embedding_dim = 200
  - Hidden Dimension: hidden_dim = 256
  - Number of RNN Layers: n_layers = 2
