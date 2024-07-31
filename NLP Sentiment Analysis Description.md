## NLP Sentiment Analysis

This repository contains a project for performing sentiment analysis on social media posts and product reviews using Natural Language Processing (NLP). The project leverages the Hugging Face `transformers` library and `pipeline` API to simplify the process of sentiment analysis.

### Features

- **Sentiment Analysis**: Classify texts as positive or negative with confidence scores.
- **Pre-trained Models**: Utilize pre-trained models for robust and accurate sentiment predictions.
- **Sample Dataset**: Includes examples of social media posts and product reviews for demonstration purposes.

### Installation

To get started, clone this repository and install the required dependencies:

```bash
git clone https://github.com/your-username/NLP-Sentiment-Analysis.git
cd NLP-Sentiment-Analysis
pip install -r requirements.txt
```

### Usage

1. **Run the Script**: Use the provided script to perform sentiment analysis on sample texts.
   ```python
   from transformers import pipeline

   # Initialize the sentiment-analysis pipeline
   sentiment_analysis = pipeline("sentiment-analysis")

   # Sample social media posts or product reviews
   texts = [
       "I love this product! It has changed my life for the better.",
       "This is the worst thing I have ever bought. Completely useless.",
       "Had an amazing experience with their customer service.",
       "The product is okay, not too bad but not great either."
   ]

   # Perform sentiment analysis on the texts
   for text in texts:
       result = sentiment_analysis(text)[0]
       print(f"Text: {text}")
       print(f"Sentiment: {result['label']}, Score: {result['score']:.4f}\n")
   ```

2. **Notebook**: Alternatively, you can explore the project using the provided Jupyter notebook `NLP Sentiment Analysis.ipynb`.

### Dependencies

- `torch`
- `transformers`

### Contributing

Contributions are welcome! If you have any suggestions or improvements, feel free to open an issue or submit a pull request.

### License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

### Acknowledgments

- Hugging Face for providing the `transformers` library and pre-trained models.
