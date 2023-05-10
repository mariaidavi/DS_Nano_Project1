# Airbnb Prices Prediction (Seattle)

This repository contains the code and data for my blog post about using Lasso regression to predict Airbnb prices. In the post, I explore a dataset of Airbnb listings in Seattle and use a Lasso model to identify the most important features that contribute to those prices.

Our motivation was to explore the potential of applying Data Science on real-world business questions such as the following:
1. Which appartment's features will give the host the opportunity to -easily- to charge more?
2. What are the most desired areas of Seattle, for Airbnb guests?
3. What are some key recommendations for the host?

## Contents

- [Blogpost](https://github.com/mariaidavi/DS_Nano_Project1/blob/main/Blog%20Post.md)
- `calendar.csv`: the raw data file downloaded from [Kaggle](https://www.kaggle.com/datasets/airbnb/seattle)
- `listings.csv`: the raw data file downloaded from [Kaggle](https://www.kaggle.com/datasets/airbnb/seattle)
- `Proyecto 1 Udacity.ipynb`: a Jupyter notebook with the code for the Lasso model

## Dependencies

The code requires the following Python packages:

- pandas
- scikit-learn
- matplotlib
- numpy
- zipfile

To install these packages, you can use pip:

```
pip install pandas scikit-learn matplotlib
```

## License

The code and data are licensed under the [MIT License](https://opensource.org/licenses/MIT).
