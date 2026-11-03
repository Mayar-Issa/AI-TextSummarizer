# AI Text Summarizer

Turns a long article into a short, readable summary using a pretrained **transformer model** from Hugging Face.

`Python` · `Hugging Face Transformers` · `PyTorch` · `NLP`

## How it works

1. Load a summarization pipeline: `pipeline("summarization")` from the `transformers` library.
2. Pass in a long text (the notebook uses a marketing article about product value).
3. Get an abstractive summary between 30 and 130 tokens long, so the model writes new sentences instead of copying them.

```python
from transformers import pipeline

summarizer = pipeline("summarization")
summary = summarizer(article, max_length=130, min_length=30, do_sample=False)
print(summary[0]["summary_text"])
```

## Run it

```bash
pip install -r requirements
```

Open `Text Summarization.ipynb` and run all cells. The model downloads automatically the first time.

**Ideas for the next version:** pick a model on purpose (BART, T5, or Arabic models), split long documents into chunks, and add a simple web interface.

---

Made by **Mayar Issa**. More projects: [mayar-issa.netlify.app](https://mayar-issa.netlify.app)
