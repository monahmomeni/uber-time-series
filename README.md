# Bayesian time series prediction

End to end implementation of paper [Deep and Confident Prediction for Time Series at Uber](https://arxiv.org/abs/1709.01907) in PyTorch. We use the [Metro Interstate Traffic Volume](https://archive.ics.uci.edu/ml/datasets/Metro+Interstate+Traffic+Volume) multivariate time series dataset for training and eventually predicting traffic volume.

We make use of the implementation of [variational dropout](https://arxiv.org/abs/1512.05287) from [keitakurita/Better_LSTM_PyTorch](https://github.com/keitakurita/Better_LSTM_PyTorch) for the LSTM layers with dropout.

## Workflow
[!model architecture](docs/architecture.png)
Code is prototyped in the notebooks in [`notebooks`](notebooks) before being transferred into cleaned up Python scripts for reuse.

- [`notebooks/01_dataset_creation.ipynb`](notebooks/01_dataset_creation.ipynb)
  - Download dataset from UCI repository, preprocessing, cleaning and feature creation
  - → [`src/data.py`](src/data.py)
- [`notebooks/02_encoder_decoder.ipynb`](notebooks/02_encoder_decoder.ipynb)
  - Prototype the encoder-decoder pretraining part of the model
  - → [`models/encoder_decoder.py`](models/encoder_decoder.py)

- `notebooks/03_autoencoder_dropout.ipynb`
- `notebooks/04_pretraining_hyperparam.ipynb`
- `notebooks/05_prediction_network.ipynb`
- `notebooks/06_full_model.ipynb`
- `notebooks/07_hyperparam_search.ipynb`
- `notebooks/08_evaluation.ipynb`



## Plots
![Time series predictions 12 steps (hours) into the future with confidence bands](docs/predictions.png)


## Requirements
```
numpy
pandas
torch
tqdm
matplotlib
```
