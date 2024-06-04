# Finetning DistilBERT for Multiclass Text Classification

This repo consists of my experimentation of researching and fine-tuning LLMs for texts classification using the Big Five Personality Traits

```DTB_multiclass_ocean.ipynb``` is the final, best-performing finetuned DistilBERT model with 94% accuracy

## Data Cleaning

### MTHR/OCEAN

The ```DTB_multiclass_ocean.ipynb``` notebook is using the [MTHR/OCEAN dataset](https://huggingface.co/datasets/MTHR/OCEAN?row=0) from hugging face.

Original data file: ```data/OCEAN-synthetic.csv```

I did data cleaning and augmentation at ```data_cleaning/clean_ocean.ipynb``` to improve the quality of data and ensure the data is balanced

Result data file: ```data/ocean_longer.csv```

## Fine-tuning
