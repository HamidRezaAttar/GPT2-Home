﻿<h1 align="center">HomeGPT2 🏠</h1>

# How to use

You can use this model directly with a pipeline for text generation:

## Pre Requirements

```bash
pip install -U transformers
```

## How to generate using pipeline

```python
from transformers import pipeline

def  remove_repetitions(text):
	first_ocurrences = []
	for sentence in text.split("."):
		if sentence not  in first_ocurrences:
			first_ocurrences.append(sentence)
	return  '.'.join(first_ocurrences)

def  trim_last_sentence(text):
	return text[:text.rfind(".")+1]

def  clean_txt(text):
	return trim_last_sentence(remove_repetitions(text))

generator = pipeline('text-generation', 'HamidRezaAttar/gpt2-product-description-generator')

query = input("Please enter your text prompt: ")

generated_text = clean_txt(generator(query)[0]['generated_text'])

print(generated_text)
```

# Run a quick Demo

|      Notebook      |                                                                                                                                                                                                 |
|:------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Test Outputs | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/HamidRezaAttar/gpt-2-home-product-description-generation/blob/main/notebooks/gpt_2_home_product_description_generation.ipynb) |



# How to fine-tune GPT-2
You can fine tune GPT-2 on any text-generation task using fastai library.
| Notebook       |                                                                                                                                                                                                |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| fine-tune GPT-2 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fastai/fastai/blob/master/nbs/39_tutorial.transformers.ipynb) |

# Citation info
```bibtex
@misc{HomeGPT2,
  author = {HamidReza Fatollah Zadeh Attar},
  title = {HomeGPT2 the English product description generator},
  year = {2021},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/HamidRezaAttar/gpt-2-home-product-description-generation}},
}
```

# Questions?
Post a Github issue on the [Issues](https://github.com/HamidRezaAttar/gpt-2-home-product-description-generation/issues) repo.
