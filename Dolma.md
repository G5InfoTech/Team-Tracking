```markdown
# Dolma Dataset

![Dolma Logo](https://huggingface.co/datasets/allenai/dolma/resolve/main/dolma_logo.png)

Dolma is a dataset of 3 trillion tokens from a diverse mix of web content, academic publications, code, books, and encyclopedic materials. It is openly released under AI2's ImpACT license as a medium risk artifact.

## Versions

At the moment, there are five versions of Dolma available:

| Version     | Default? | Release Date | Size (gzip) | Description                                                                                     |
|-------------|----------|--------------|-------------|--------------------------------------------------------------------------------------------------|
| v1_6        | ✅        | 2024-01-31   | 5.4 TB      | The latest version of Dolma, with 3 trillion tokens from a diverse mix of web content, academic publications, code, books, and encyclopedic materials. |
| v1_6-sample |          | 2024-01-31   | 16.4 GB     | A smaller sample of Dolma, with roughly 10 billion tokens. Useful for data exploration.        |
| v1_5        |          | 2023-10-31   | 6.4 TB      | The version of Dolma used to train OLMo-1B. Roughly 3 trillion tokens.                         |
| v1_5-sample |          | 2023-10-31   | 2.9 TB      | A sample of roughly 1.9 trillion tokens used to train OLMo-7B                                  |
| v1          |          | 2023-08-18   | 6.0 TB      | The first version of Dolma.                                                                     |

(Size difference between v1_6 and previous version is due to different set of metadata included in files: we removed redundant metadata in v1_6.)

## Summary Statistics (v1.6)

| Source             | Doc Type     | UTF-8 bytes (GB) | Documents (millions) | Unicode words (billions) | Llama tokens (billions) |
|-------------------|-------------|------------------|----------------------|-------------------------|------------------------|
| Common Crawl      | web pages  | 9,022            | 3,370                | 1,775                   | 2,281                  |
| The Stack         | code       | 1,043            | 210                  | 260                     | 411                    |
| C4                | web pages  | 790              | 364                  | 153                     | 198                    |
| Reddit            | social media | 339              | 377                  | 72                      | 89                     |
| PeS2o             | STEM papers | 268              | 38.8                 | 50                      | 70                     |
| Project Gutenberg | books      | 20.4             | 0.056                | 4.0                     | 6.0                    |
| Wikipedia, Wikibooks | encyclopedic | 16.2             | 6.2                  | 3.7                     | 4.3                    |
| Total             |            | 11,519           | 4,367                | 2,318                   | 3,059                  |

## Download

The fastest way to download Dolma is to clone this repository and use the files in the url directory. We recommend using wget in parallel mode to download the files. For example:

```bash
DATA_DIR="<path_to_your_data_directory>"
PARALLEL_DOWNLOADS="<number_of_parallel_downloads>" 
DOLMA_VERSION="<version_of_dolma_to_download>"

git clone https://huggingface.co/datasets/allenai/dolma
mkdir -p "${DATA_DIR}"

cat "dolma/urls/${DOLMA_VERSION}.txt" | xargs -n 1 -P "${PARALLEL_DOWNLOADS}" wget -q -P "$DATA_DIR"
```

Then, to load this data using HuggingFace's datasets library, you can use the following code:

```python
import os
from datasets import load_dataset

os.environ["DATA_DIR"] = "<path_to_your_data_directory>"
dataset = load_dataset("allenai/dolma", split="train")
```

## Citation

If you use our dataset or tooling, please cite us at:

```bibtex
@article{dolma,
  title = {{Dolma: an Open Corpus of Three Trillion Tokens for Language Model Pretraining Research}},
  author={
    Luca Soldaini and Rodney Kinney and Akshita Bhagia and Dustin Schwenk and David Atkinson and
    Russell Authur and Ben Bogin and Khyathi Chandu and Jennifer Dumas and Yanai Elazar and 
    Valentin Hofmann and Ananya Harsh Jha and Sachin Kumar and Li Lucy and Xinxi Lyu and
    Nathan Lambert and Ian Magnusson and Jacob Morrison and Niklas Muennighoff and Aakanksha Naik and
    Crystal Nam and Matthew E. Peters and Abhilasha Ravichander and Kyle Richardson and Zejiang Shen and
    Emma Strubell and Nishant Subramani and Oyvind Tafjord and Pete Walsh and Luke Zettlemoyer and
    Noah A. Smith and Hannaneh Hajishirzi and Iz Beltagy and Dirk Groeneveld and Jesse Dodge and Kyle Lo
  },
  year = {2024},
  journal={arXiv preprint},
}
```
```
