# Parameter-Efficient Fine-Tuning with Low-Rank Adaptation for Text Classification


## Project Overview

This repository contains our implementation for efficient fine-tuning of RoBERTa using Low-Rank Adaptation (LoRA) for the AG News text classification task.
### Key Features

- Parameter-efficient fine-tuning using LoRA adapters
- RoBERTa-base as the foundation model
- Text classification for AG News dataset (4 categories)
- Under 1 million trainable parameters
- 94.59% test accuracy

## Dataset

The AG News dataset consists of approximately 120,000 news articles categorized into four classes:
- World
- Sports
- Business
- Sci/Tech

## Implementation Details

We fine-tuned the RoBERTa-base model using LoRA with the following configuration:
- Rank (r): 6
- Alpha (α): 24
- LoRA dropout: 0.1
- Target modules: query, key, and value matrices in attention layers
- Trainable parameters: 925,444 (0.737% of total)

## Results

- Training accuracy: 94.85%
- Validation accuracy: 94.10%
- Test accuracy: 94.59%
- F1 scores per class:
  - World: 0.95
  - Sports: 0.99
  - Business: 0.92
  - Sci/Tech: 0.92
- Kaggle competition scores:
  - Public leaderboard: 0.84625
  - Private leaderboard: 0.84900

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/Sharayu1418/LoRA-Fine-Tuning.git
cd LoRA-Fine-Tuning
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the notebook or training script:
```bash
jupyter notebook notebooks/LoRA-Fine-Tuning.ipynb
```

## Citation

If you use this code, please cite the following papers:

```
@article{hu2021lora,
  title={LoRA: Low-Rank Adaptation of Large Language Models},
  author={Hu, Edward J and Shen, Yelong and Wallis, Phillip and Allen-Zhu, Zeyuan and Li, Yuanzhi and Wang, Shean and Wang, Lu and Chen, Weizhu},
  journal={arXiv preprint arXiv:2106.09685},
  year={2021}
}

@article{liu2019roberta,
  title={RoBERTa: A Robustly Optimized BERT Pretraining Approach},
  author={Liu, Yinhan and Ott, Myle and Goyal, Naman and Du, Jingfei and Joshi, Mandar and Chen, Danqi and Levy, Omer and Lewis, Mike and Zettlemoyer, Luke and Stoyanov, Veselin},
  journal={arXiv preprint arXiv:1907.11692},
  year={2019}
}
```

-----
