# Finetuning DistilBERT for Multiclass Text Classification

This repository contains two text classification models designed for specific NLP tasks:

- **Personality Detector Model**: Finetuned to detect personality traits from texts based on the Big Five personality framework. 

- **Negative Statement Detector Model**: Specifically trained to identify negative statements in texts, improving the accuracy of the Personality Detector Model.

## Application

Both finetuned models are accessible on my Hugging Face account: [joycerlz/distilbert-personality](https://huggingface.co/joycerlz/distilbert-personality) and [joycerlz/distilbert-binary-polar](https://huggingface.co/joycerlz/distilbert-binary-polar)

## Data Cleaning

### MTHR/OCEAN

The ```DTB_multiclass_ocean.ipynb``` notebook is using the [MTHR/OCEAN dataset](https://huggingface.co/datasets/MTHR/OCEAN?row=0) from hugging face.

Original data file: ```data/OCEAN-synthetic.csv```

I did data cleaning and augmentation at ```data_cleaning/clean_ocean.ipynb``` to improve the quality of data and ensure the data is balanced

Result data file: ```data/ocean_longer.csv```

### Negating sentences

To prepare dataset for training the the negative statement detection model, I used the [negate](https://github.com/dmlls/negate) library to negate all sentences, and assign the labels accrodingly. The work is also under the ```data_cleaning/clean_ocean.ipynb``` notebook.

Result data file: ```data/ocean_isPos.csv```

## Fine-tuning

### Personalilty detection model

Notebook: ```DTB_multiclass_ocean.ipynb``` 

Data file: ```data/ocean_longer.csv```

I'm using [Hugging Face's](https://huggingface.co/distilbert/distilbert-base-uncased) ```distilbert-base-uncased```, I added 2 dropout layers and 2 dense layers to make the model more complex and improve its performance.

Accuracy: 94%

![ocean report](https://github.com/joycerlz/bigfive-text-classification/assets/81258562/648f9546-018c-4491-b307-b9239e06610b)


### Negative statement detection model

Notebook: ```polarity.ipynb``` 

Data file: ```data/ocean_isPos.csv```

After fintuning the initial personality detection model, during testing, I encountered issues with the model's handling of sentences containing negative modifiers like "never" and "not." My solution was to finetune another model specifically for detecting this kind of negative words, and reverse the results accrodingly. This model improved the overall accuracy and reliability of the personality detection system.

