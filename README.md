# Jungle Book Character-level LSTM

Simple character-level LSTM text generator trained on The Jungle Book The model learns sequences of characters and predicts the next character to generate new text.

## Repository contents
- `the_jungle_book.txt` (expected under `files/`): input corpus (Project Gutenberg).
- Training script containing model code.
- `saved_weights/`: checkpoint files saved during training.
- `my_saved_weights_jungle_book_50epochs.h5`: final model weights.
- `README.md`: documentation.

## Requirements
- Python 3.8+
- TensorFlow / Keras
- numpy
- pillow
- matplotlib

Install dependencies:
```
pip install numpy matplotlib tensorflow pillow
```

## Data
Download the plain text of The Jungle Book from:
http://www.gutenberg.org/ebooks/236  
Save as UTF-8 under `files/the_jungle_book.txt`.

## How to train
```
python train_lstm.py
```
This will:
- Load and clean text
- Vectorize characters
- Train an LSTM model
- Save checkpoints in `saved_weights/`
- Save final weights as `my_saved_weights_jungle_book_50epochs.h5`

## How to generate text
After training:
- The script loads saved weights
- Picks a random seed sequence
- Generates text character-by-character

Control output length by adjusting:
```
for i in range(400):
```

## Configuration
- `seq_length`: input sequence length (default 60)
- `step`: sliding window step (default 10)
- Model: LSTM(128), can be increased or stacked

## Notes
- Training is faster on GPU
- Character models struggle with long-range coherence
- One-hot encoding is memory heavy
- Improve output using:
  - more epochs
  - larger model
  - temperature-based sampling

## Attribution
- Author of base script: Sreenivas Bhattiprolu
- Data: Project Gutenberg – The Jungle Book

## License
Add your preferred license.
