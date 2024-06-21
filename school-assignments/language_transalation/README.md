# French-English Translation Project

## Dataset Creation and Preprocessing Steps
1. **Data Collection**:
    - The dataset is sourced from a CSV file named `french_eng.csv`.

2. **Preprocessing**:
    - The dataset is loaded using Pandas and any unnamed columns are dropped.
    - Input (English) and target (French) texts are separated.
    - Tokenization is performed on both input and target texts using TensorFlow's `Tokenizer`.
    - Sequences are padded to ensure uniform length using TensorFlow's `pad_sequences`.

## Model Architecture and Design Choices
1. **Model Selection**:
    - A sequence-to-sequence model with an LSTM architecture is chosen due to its effectiveness in handling sequential data for translation tasks.

2. **Architecture Details**:
    - **Encoder**:
        - Input layer with shape `(None,)`.
        - Embedding layer with vocabulary size and embedding dimension.
        - The LSTM layer with the return state is enabled to output the encoder states.
    - **Decoder**:
        - Input layer with shape `(None,)`.
        - Embedding layer for the target vocabulary.
        - LSTM layer with return sequences and return state enabled.
        - Dense layer with softmax activation to output probabilities over the target vocabulary.

3. **Design Choices**:
    - The embedding dimension is set to 256 and the number of LSTM units is 512.
    - The model is compiled with the Adam optimizer and sparse categorical cross-entropy loss function.

## Training Process and Hyperparameters Used
1. **Training Setup**:
    - Environment: TensorFlow and Keras libraries.
    - Data split: 80% training, 20% validation.

2. **Hyperparameters**:
    - Batch size: 128
    - Epochs: 30

3. **Training Procedure**:
    - The target sequences are shifted by one position for teacher forcing during training.
    - The model is trained using the `.fit()` method with validation split of 20%.

## Evaluation Metrics and Results
1. **Metrics**:
    - The primary metric used for evaluation is the loss (sparse categorical cross-entropy).

2. **Results**:
    - The model's performance is evaluated on the validation set.
    - Training and validation loss can be plotted to show the model's learning progress over epochs.

## Insights and Potential Improvements
1. **Analysis**:
    - The model shows reasonable translation accuracy but may struggle with longer sentences due to the fixed sequence length.

2. **Limitations**:
    - The model might not generalize well to sentences significantly longer than those seen during training.
