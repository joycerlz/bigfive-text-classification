# Fine Tuning DistilBERT for Multiclass Text Classification

Notebook for fine tuning the DistilBERT model, accuracy 99%


## Data for training

### Big five personality trait scores
```data/big_five_scores.csv, data/trait_scoring_keys.csv```

See combine_oversample_df.ipynb for preparing, cleaning and oversampling the dataset. Resulting file is ```data/augmented_df.csv```

Data source: [automoto/big-five-data](https://github.com/automoto/big-five-data?tab=readme-ov-file)


### Stream of consciousness essays 
```data/essays.csv, data/mypersonality_final.csv```

This is the scientific gold standard from psychology, controlled environment collected stream of consciousness by James Pennebaker and Laura King labelled with Big Five personality traits. See: http://web.archive.org/web/20160519045708/http://mypersonality.org/wiki/doku.php?id=wcpr13
