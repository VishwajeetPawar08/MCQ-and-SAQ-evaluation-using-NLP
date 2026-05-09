# Irish to English Speech Translation (NLP Assignment 2)

Hi, this is my code and report for the NLP module assignment 2. The project is about translating spoken Irish audio into English text. Since Irish is a low resource language, I built a cascaded pipeline which does speech recognition first, and then translates the text.

## What is in this project

I built two pipelines to compare them:

* **Baseline System:** I used the `Semih/wav2vec2_Irish_Large` model to turn Irish speech into Irish text. Then I used `facebook/nllb-200-distilled-1.3B` to translate it into English.
* **Improved System:** I keep the same speech model but changed the translation model to `Helsinki-NLP/opus-mt-ga-en`. I did this because the Helsinki model is trained specially for Irish to English, so it gives better translation.

## Results

I tested this on 50 audio samples from the IWSLT 2026 dataset. Here is how they did:

| System | BLEU Score | chrF++ Score |
| :--- | :--- | :--- |
| Baseline (NLLB) | 1.42 | 17.01 |
| Improved (Opus-MT) | 2.01 | 16.01 |

The new model got a better BLEU score but a slightly lower chrF++ score. Most of the mistakes actually came from the speech recognition part mishearing Irish words, which confused the translation model later. 

## How to run the code

1. Open the Jupyter Notebook file in Google Colab.
2. Change your runtime available GPU so it runs faster.
3. Run the cells from top to bottom. The code will automatically download the dataset from GitHub.
4. Wait for it to download the models. It might take few minutes.
5. The final results and transcripts will be saved in a `results` folder.

## Files Included

* The Jupyter notebook with all the code.
* The PDF report explaining my methods and error analysis.
* This README file.
* Result folder with txt and csv file
