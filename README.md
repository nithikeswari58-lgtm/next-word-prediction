
readme_content = """
# Next-Word Prediction Using LSTM

## 1. Project Overview
This project predicts the next word in a text sequence using
a Long Short-Term Memory (LSTM) neural network. It uses
Natural Language Processing (NLP) techniques to process text
and learn word sequence patterns.

## 2. Objectives
- Tokenize the text corpus and construct a vocabulary.
- Generate input-target word sequences.
- Train an LSTM-based next-word prediction model.
- Evaluate the model using Top-1 and Top-5 accuracy.
- Compare model performance using different corpus sizes.
- Predict the next word for at least five input phrases.

## 3. Dataset
Dataset file: `medium_data.csv`

Source:
https://www.kaggle.com/datasets/hsankesara/next-word-prediction

The downloaded CSV contains 6,508 rows of article metadata,
including titles and subtitles. Since full article text was
not available in this file, titles and subtitles were used
to construct the text corpus.

After cleaning and filtering, approximately 7,307
sentence-like samples were available.

**Dataset limitation:** The corpus contains title/subtitle
text rather than complete article bodies, and it does not
meet the target of 10,000 full sentences.

## 4. Technologies Used
- Python
- Google Colab
- Pandas and NumPy
- TensorFlow and Keras
- Scikit-learn
- LSTM neural network

## 5. Methodology
1. Load and inspect the CSV dataset.
2. Combine available titles and subtitles.
3. Clean and prepare the text.
4. Tokenize the text and build the vocabulary.
5. Generate input-target sequences.
6. Pad sequences to a fixed length.
7. Build and train the LSTM model.
8. Evaluate Top-1 and Top-5 accuracy.
9. Predict next words for five phrases.
10. Compare performance across different training-data sizes.

## 6. Model Architecture
- Embedding dimension: 64
- LSTM units: 64
- Dropout rate: 0.2
- Maximum context length: 5 words
- Output layer: Dense with Softmax activation
- Optimizer: Adam
- Loss function: Sparse categorical cross-entropy
- Training epochs: 8

Total trainable parameters: 1,156,098

## 7. Main Model Results
| Metric | Result |
|---|---:|
| Training accuracy | 12.91% |
| Validation accuracy | 11.58% |
| Test Top-1 accuracy | 12.01% |
| Test Top-5 accuracy | 24.16% |
| Test loss | 6.7662 |

## 8. Sample Predictions
The model was tested with five input phrases:
- a beginner's guide to
- graph neural networks with
- how to use
- machine learning
- data science

The model generated five possible next-word predictions
for each phrase.

## 9. Corpus Size Experiment
| Training data | Sentences | Top-1 accuracy | Top-5 accuracy |
|---|---:|---:|---:|
| 25% | 1,461 | 3.87% | 13.69% |
| 50% | 2,922 | 3.87% | 13.45% |
| 100% | 5,845 | 3.87% | 13.45% |

These subset experiments used smaller models and up to
three epochs. No clear improvement was observed as the
training subset increased. More experiments are needed
to determine the effect of corpus size reliably.

## 10. Limitations
- Full article bodies were unavailable in the downloaded CSV.
- Some text samples may combine titles and subtitles imperfectly.
- The available corpus is smaller than the 10,000-sentence target.
- Prediction accuracy is limited and can be improved.
- Corpus-size experiments used a simplified training setup.

## 11. Future Improvements
- Use a larger corpus containing complete sentences.
- Improve sentence-boundary detection.
- Tune model architecture and training parameters.
- Compare LSTM with GRU and Transformer models.
- Train and evaluate with additional data.

## 12. How to Run
1. Open the Jupyter notebook in Google Colab.
2. Upload `medium_data.csv` when prompted.
3. Run the notebook cells in order.
4. Review the training metrics, predictions, and evaluation results.

## 13. Conclusion
An LSTM-based next-word prediction model was implemented
and evaluated. The model produced next-word suggestions
and was evaluated using Top-1 and Top-5 accuracy. The
results show that corpus quality, dataset size, and model
training are important factors for improving prediction
performance.
"""

with open("README.md", "w", encoding="utf-8") as file:
    file.write(readme_content.strip() + "\n")

print("README.md created successfully!")
