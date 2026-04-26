# English Accent Classification Project

Final project for Language Processing course at UTEP.

## Description

This project focuses on classifying English accents using machine learning techniques. To evaluate the progression of audio processing technology, we implement a Dual-Path Architecture comparing traditional acoustic phonetics against deep learning models:

1. Traditional Path (MFCC): Extracts 40 Mel-frequency cepstral coefficients to analyze the physical shape of the sound waves.
2. Neural AI Path (WavLM): Utilizes Microsoft's pre-trained WavLM-Base transformer to extract deep, context-aware linguistic embeddings.

## Dataset

The data is sourced from the Mozilla Common Voice dataset.

- Classes: American, British, Australian, Indian.
- Format: 16kHz, normalized, padded/trimmed to exactly 3.0 seconds.
- Evaluation: Strict isolation. Models are trained on train.tsv (6,000 samples per accent) and evaluated on an unseen test.tsv (1,200 samples per accent).

## Key Findings

- The deep learning approach (WavLM) significantly outperformed traditional acoustics (~88% vs ~65% accuracy). This demonstrates that accents rely heavily on linguistic context and prosody, which pure mathematical wave analysis struggles to capture.
- Both models found the American accent the hardest to classify. This is likely due to the massive regional dialect diversity within the United States data compared to the highly distinct phonetic markers of the Indian accent.

## Team Members

- Victor Hermosillo
- Gael Sustaita
- Benjamin Muñiz

## Files

- Final_Project_Accent_detection.ipynb - Main Jupyter notebook containing the accent classification implementation
- requirements.txt - Python package dependencies
- .env - (To be created locally) Contains the Hugging Face token required for WavLM

## Setup

1. Clone the repository

```bash
git clone [https://github.com/VictorHermosillo07/english-accent-classification.git](https://github.com/VictorHermosillo07/english-accent-classification.git)
cd english-accent-classification
```

2. Create a virtual environment and install dependencies

```bash
python3 -m venv venv
source venv/bin/activate
# On Windows: venv\Scripts\activate
```

3. Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

4. Create a `.env` file in the root directory and add your Hugging Face token

```
HF_TOKEN=your_token_here
```
