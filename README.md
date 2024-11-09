# YouTube Video Slide Extractor with Text Recognition and PowerPoint Export

This Streamlit app converts YouTube videos into PowerPoint presentations by extracting unique slides, applying Optical Character Recognition (OCR) to detect text, and generating a downloadable PowerPoint (.pptx) file. It’s designed for educators, students, professionals, or anyone who needs to quickly convert video content into organized, text-annotated slides.

## Features

- **YouTube Video Download**: Provide a YouTube URL to download the video in the best available quality.
- **Frame Extraction**: Extract frames at regular intervals to capture key slides or visuals.
- **Unique Slide Detection**: Filters out duplicate frames using perceptual hashing to ensure only unique slides are included.
- **Text Recognition (OCR)**: Extracts text from the slides using Tesseract OCR.
- **PowerPoint Export**: Generates a PowerPoint presentation with slides and recognized text, ready for download.

## Stack

- **Python**: For backend processing.
- **uv**: For [Python package and project managment](https://docs.astral.sh/uv).
- **Streamlit**: For the user interface.
- **OpenCV** and **PIL**: For video processing and frame extraction.
- **imagehash**: For perceptual hashing to detect unique slides.
- **pytesseract**: For Optical Character Recognition (OCR) to extract text from slides.
- **python-pptx**: To generate PowerPoint files.
- **yt-dlp**: To download videos from YouTube.

## Installation

### 1. Clone the repository
```bash
git clone git@github.com:Adityakeshav/youtube-slide-extractor.git
cd youtube-slide-extractor
```

### 2. Install required dependencies
Ensure `Python 3.11>=` is installed, then install the necessary packages:
```bash
python3.11 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

or with fast `uv`
```bash
uv venv --python=python3.11
source .venv/bin/activate
uv pip install -r requirements.txt
```

### 3. Install resseract OCR
You’ll need Tesseract OCR for text recognition. Follow the installation instructions for your OS:

- **Windows**: Download from [Tesseract OCR's official repository](https://github.com/tesseract-ocr/tesseract).
- **Linux**: Install via package manager:
  ```bash
  sudo apt install tesseract-ocr
  ```
- **macOS**: Use Homebrew:
  ```bash
  brew install tesseract
  ```

Ensure Tesseract is added to your system’s PATH.

## Usage

1. Run the Streamlit app:
    ```bash
    streamlit run app.py
    ```

2. Open the app in your browser. You will see a text input field to enter a YouTube video URL.

3. Enter the URL of the YouTube video you wish to convert into a PowerPoint.

4. Click **Process Video**. The app will download the video, extract frames, detect unique slides, apply OCR to extract text, and create a PowerPoint file.

5. After processing, you can review the slides and text extracted. You can then download the PowerPoint file directly from the app.

## Use cases

- **Educational Content**: Convert video lectures into PowerPoint slides.
- **Meeting Summaries**: Extract key points from recorded webinars or meetings and compile them into presentations.
- **Content Archiving**: Save slides from tutorials or presentations in a structured format.


## Develop and contributing

To compile requirements

```bash
uv pip compile requirements.in -o requirements.txt
```

uv add pip install ruff

Run on `localhost`

```bash
streamlit run app.py \
  --browser.gatherUsageStats false \
  --server.headless true \
  --browser.serverAddress localhost
```

To `format` the code

```bash
uv run ruff format
```
