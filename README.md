# Summer 2024, W266 Final Project
**Authors:** Jian Wu, Mehmet Inonu

Our final project fine-tuned the BERT uncased model with domain-specific knowledge to classify political ideology—whether left, right, or center—in news articles that may unconsciously influence and mislead readers.

## Dataset

The dataset consists of articles crawled from [www.allsides.com](http://www.allsides.com) and is available in the `./data` folder. The dataset includes various evaluation splits.

### Overview

- **Total Articles:** 37,554
- **Article Format:** JSON

### Article Fields

Each article is stored as a JSON object in the `./data/jsons` directory and includes the following fields:

- **ID:** An alphanumeric identifier.
- **topic:** The topic being discussed in the article.
- **source:** The name of the article's source (e.g., New York Times).
- **source_url:** The URL to the source's homepage (e.g., [www.nytimes.com](http://www.nytimes.com)).
- **url:** The link to the actual article.
- **date:** The publication date of the article.
- **authors:** A comma-separated list of the article's authors.
- **title:** The article's title.
- **content_original:** The original body of the article, as returned by the newspaper3k Python library.
- **content:** The processed and tokenized content, used as input to the models.
- **bias_text:** The label of the political bias annotation of the article (left, center, or right).
- **bias:** The numeric encoding of the political bias of the article (0, 1, or 2).

### Dataset Splits

The `./data/splits` directory contains two types of splits, as discussed in the paper:

- **Random**
- **Media-Based**

For each type, the directory provides train, validation, and test files containing the articles' IDs and their numeric bias labels.

## Dataset Citation

```bibtex
@inproceedings{baly2020we,
  author      = {Baly, Ramy and Da San Martino, Giovanni and Glass, James and Nakov, Preslav},
  title       = {We Can Detect Your Bias: Predicting the Political Ideology of News Articles},
  booktitle   = {Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP)},
  series      = {EMNLP~'20},
  NOmonth     = {November},
  year        = {2020},
  pages       = {4982--4991},
  NOpublisher = {Association for Computational Linguistics}
}
