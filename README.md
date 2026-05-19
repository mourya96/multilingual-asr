# Multilingual Automatic Speech Recognition

This project evaluates the performance improvement of an Automatic Speech Recognition (ASR) system by comparing a zero-shot baseline (Whisper Large v3 Turbo) against a fine-tuned version. It involves running comprehensive inference on a test dataset and computing the Word Error Rate (WER) metrics.

## Prerequisites

- Python >= 3.12
- `uv` package manager (recommended) or `pip`
- CUDA-compatible GPU (recommended for faster inference)

## Installation

1. Clone the repository and navigate to the project directory:
   ```bash
   git clone <repository_url>
   cd multilingual-speech-recognition
   ```

2. Install dependencies:
   If using `uv` (recommended):
   ```bash
   uv sync
   # or
   uv venv
   source .venv/bin/activate
   uv pip install -e .
   ```
   Or using standard `pip`:
   ```bash
   pip install .
   ```

## Dataset Structure

The dataset is expected to be placed under the `audio_data/` directory. For example, the test data should be organized as follows:
- `audio_data/test.csv`: Contains metadata such as the `audio` filename and true `text` transcriptions.
- `audio_data/test/`: Contains the actual `.wav` or audio files corresponding to the filenames in the CSV.

## Scripts and Usage

### 1. Compute Word Error Rate (WER)
After extracting the dataset, you can evaluate the models and compute the Word Error Rate (WER). The script evaluates both the `openai/whisper-large-v3-turbo` baseline and the fine-tuned model, comparing their results.
Run the evaluation:
```bash
python compute_wers.py
```

### 2. Notebooks
- `audio_eda.ipynb`: A Jupyter Notebook containing Exploratory Data Analysis (EDA) on the audio data.
- `multilanguage-speech-recognition.ipynb`: A Notebook documenting the main training/exploration workflow for the project.

## Project Structure

```
multilingual-speech-recognition/
├── pyproject.toml         # Project dependencies and metadata
├── uv.lock                # Locked dependencies for reproducibility
├── audio_eda.ipynb        # EDA notebook for audio data
├── whsiper-training.ipynb # Main training/workflow notebook
├── inference.ipynb        # Inference workflow notebook
├── audio_data/            # Directory containing the dataset
└── models/                # Directory containing downloaded/finetuned models
```
