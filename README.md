# Fine Tuning LLM for Multilabel Text Classification

Fine tuning LLMs for classifying the Big Five Personality texts

[This doc](https://docs.google.com/document/d/13EYNjZmiPtRzb34k3gXyNyjMSfHlD0emY1oKaDg_kfQ/edit) records some of the models I've tried so far

## Data for training

### Big five personality trait scores
```data/big_five_scores.csv, data/trait_scoring_keys.csv```

See combine_oversample_df.ipynb for preparing, cleaning and oversampling the dataset. Resulting file is ```data/augmented_df.csv```

Data source: [automoto/big-five-data](https://github.com/automoto/big-five-data?tab=readme-ov-file)


### Stream of consciousness essays 
```data/essays.csv, data/mypersonality_final.csv```

This is the scientific gold standard from psychology, controlled environment collected stream of consciousness by James Pennebaker and Laura King labelled with Big Five personality traits. See: http://web.archive.org/web/20160519045708/http://mypersonality.org/wiki/doku.php?id=wcpr13


### Kaggle

Found [here](https://www.kaggle.com/datasets/zeeshanaliii/big-five-dataset?select=big_five_val_set.csv), no explanation was provided

Cleaned file is ```data/kaggle_cleaned.csv```, using ```prepare_bigfive_kaggle.ipynb```
