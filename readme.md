# Audiobook Creator

## Description

This project demonstrates how to create an audiobook from a PDF file using Python. It involves extracting text from the PDF, cleaning the text, converting it into speech, and saving the speech as an audio file.

## Features

* Extracts text from PDF files using PyPDF2.
* Cleans the extracted text to remove unnecessary formatting.
* Converts the cleaned text into speech using gTTS.
* Saves the generated speech as an MP3 audio file.

## Dependencies

* PyPDF2
* gTTS
* re

## Installation

1.  Install the required packages:

    ```bash
    pip install PyPDF2 gTTS
    ```

## Usage

1.  Place the PDF file you want to convert into an audiobook in the same directory as the script.
2.  Run the `AudioBook_Creator.ipynb` notebook.
3.  The script will:
    * Extract the text from the PDF file.
    * Clean the extracted text.
    * Convert the text into speech.
    * Save the speech as an MP3 file named `audio.mp3`.

## Code Description

### 1. Extract text from PDF

* Uses PyPDF2 to extract text from each page of the PDF.
    * `extract_text_from_pdf(file_path)`:
        * Opens the PDF file in binary read mode ('rb').
        * Creates a `PdfReader` object.
        * Iterates through each page of the PDF.
        * Extracts the text from each page using `page.extract_text()`.
        * Concatenates the extracted text from all pages.
        * Returns the complete text.
    * `clean_pdf_text(raw_text)`:
        * Removes hyphenation at the end of lines (`-`).
        * Replaces multiple newlines with a single space.
        * Replaces sequences of two or more spaces with a single space.
        * Removes isolated digits.
        * Returns the cleaned text.

### 2. Convert the Text into Speech

* Uses the gTTS library to convert the extracted text into speech.
    * `convert_text_to_speech(text, language='en', output_file='audio.mp3')`:
        * Creates a gTTS object with the given text and language.
        * Saves the speech to an MP3 file using `tts.save(output_file)`.
        * Prints a message indicating the file name where the audio is saved.