# Translating English to French Using Transformer Models

## Description
This project aims to enhance a literacy practice application by incorporating French, enabling bilingual practice. It involves training and evaluating two translation models: Helsinki-NLP's MarianMT and Google's T5.

## Goal
Add French language support to the existing literacy practice app [Spelling Practice 2](https://github.com/sergi-s/spelling-practice-2), improving bilingual proficiency for users.

## Models Used

### Helsinki-NLP/Opus-MT
- **Description**: Built on Marian framework, known for efficient, high-quality translations.
- **Architecture**: Utilizes Transformer architecture with self-attention mechanisms.
- **Usage**: Ideal for content localization, multilingual tools, and language learning applications.

### T5 (Text-to-Text Transfer Transformer)
- **Description**: Versatile model reframing NLP tasks as text-to-text tasks.
- **Architecture**: Features an encoder-decoder setup, preserving context and nuances.
- **Usage**: Suitable for automated content creation, conversational agents, and advanced text generation.

## Dataset

### WMT14 French-English Dataset
- **Description**: A large dataset commonly used in machine translation research.
- **Training Data Usage**: Limited by practical constraints, a subset of the data was used.
- **Training Parameters**: Batch size of 1000, 50 training batches, 3 evaluation batches.

## Data Preparation Steps

1. **Dataset Loading**: Loaded and split using `load_dataset`.
2. **Tokenization**: Tokenized with a maximum length of 128 tokens.
3. **Batch Processing**: Tokenized in batches to manage memory and time constraints.
4. **Dataset Concatenation**: Combined batches for efficient training and evaluation.
5. **Memory Optimization**: Used garbage collection to manage resources.

## Model Training and Evaluation

### Helsinki-NLP/Opus-MT
- **Training**: Fine-tuned on WMT14 dataset over three epochs.
- **Evaluation Results**: Evaluation loss of 0.5138.

### T5-small
- **Training**: Fine-tuned on WMT14 dataset under the same conditions.
- **Evaluation Results**: Lower evaluation loss of 0.3480.

## Model Output Comparison

### Translation Examples
- **Helsinki-NLP/Opus-MT**: "Hello, how are you?" -> "Bonjour, comment êtes-vous?"
- **T5**: "Hello, how are you?" -> "Bonjour, comment êtes-vous?"

### Performance Metrics

| Metric               | Helsinki-NLP/Opus-MT | T5-small       |
|----------------------|----------------------|----------------|
| Evaluation Loss      | 0.491                | 0.3475         |
| Runtime (seconds)    | 21.0922              | 16.7546        |
| Samples per Second   | 142.233              | 179.056        |
| Steps per Second     | 8.913                | 11.221         |
| BLEU Score           | 0.368                | 0.289          |
| METEOR Score         | 0.645                | 0.571          |
| TER Score            | 2435.614             | 2060.338       |

## Conclusion
T5 outperforms Helsinki-NLP/Opus-MT in METEOR score, TER score, evaluation loss, and computational efficiency, making it the recommended model for applications requiring high translation quality and efficiency.

## Colab Notebook
For detailed implementation, refer to the [Google Colab notebooks](https://colab.research.google.com/drive/1ugFwM8gNpmgkHKAKSCUpxJSrvS0m5C6C?usp=sharing) and [here](https://colab.research.google.com/drive/1Vfsn74i8nPi0R65fhqhgc8TvpYS_Erkg?usp=sharing).
