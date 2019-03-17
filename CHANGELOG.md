# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

### Added

- `PolynomialExtender`, `Discarder`, and `FuncTransformer` to `preprocessing`
- `FMRegressor` to `linear_model`
- `metrics`:
    - `Accuracy`
    - `MAE`
    - `MSE`
    - `RMSE`
    - `RMSLE`
    - `SMAPE`
    - `Precision` (binary)
    - `Recall` (binary)
    - `F1Score` (binary)
- `CategoricalImputer` to `impute`
- `stats`:
    - `Mode`
    - `Quantile`
    - `RollingQuantile`
    - `Entropy`
    - `RollingMin`
    - `RollingMax`
    - `RollingMode`
    - `RollingSum`
    - `RollingPeakToPeak`
- `convert_creme_to_sklearn` to `compat`
- `SVD` to `reco`
- `BoxCoxTransformRegressor`, `TargetModifierRegressor` to `compose`
- `iter_csv` to `stream`
- `fetch_restaurants` and `load_airline` to `datasets`
- `GaussianNB` to `naive_bayes`
- `Multinomial` and `Normal` to `dist`
- `PassiveAggressiveI` and `PassiveAggressiveII` to `optim`

### Modified

- `model_selection.online_score` now accepts a `creme` metric instead of an `sklearn` metric; it also checks that the provided metric can be used with the accompanying model
- Calling `fit_one` now returns the calling instance, not the out-of-fold prediction/transform
- `fit_predict_one`, `fit_predict_proba_one`, and `fit_transform_one` are available to reproduce the previous behavior
- Binary classifiers now output a `dict` with probabilities for `False` and `True` when calling `predict_proba_one`, which solves the interface issues of having multi-class classifiers do binary classification

### Removed

- All the passive-aggressive estimators from `linear_model`

## [0.0.2] - 2019-02-13

### Added

- Passive-aggressive models to `linear_model`
- `HedgeClassifier` to `ensemble`
- `RandomDiscarder` to `feature_selection`
- `NUnique`, `Min`, `Max`, `PeakToPeak`, `Kurtosis`, `Skew`, `Sum`, `EWMean` to `stats`
- `AbsoluteLoss`, `HingeLoss`, `EpsilonInsensitiveHingeLoss` to `optim`
- `sklearn` wrappers to `compat`
- `TargetEncoder` to `feature_extraction`
- `NumericImputer` to `impute`

### Changed

- Made sure the running statistics produce the same results as `pandas`'s `rolling` method