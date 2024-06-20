# pypots-1-feature-imputation
Modifed version of [PyPOTS](https://github.com/WenjieDu/PyPOTS) for feature imputation in Partially-Observed Time Series (POTS) with emphasis on one feature.

## Details

To put the emphasis on one feature, the loss functions are modified in such a way that only errors affecting this feature are taken into account during training.
Without loss of generality, the emphasis is put on the last feature. If you want to put emphasis on another feature, simply reorder your features prior to using the imputation models.

This code is adapted from [PyPOTS's imputation module](https://github.com/WenjieDu/PyPOTS/tree/v0.0.9/pypots/imputation).

## Usage

To activate the emphasis on one feature (the last feature), simply add the `last_feature_only = True` option in your model's constructor.

```
model = SAITS(n_steps = n_steps, n_features = n_features, n_layers = n_layers, d_model = d_model,
              d_inner = d_inner, n_head = n_head, d_k = d_k, d_v = d_v, dropout = dropout)
```

becomes

```
model = SAITS(n_steps = n_steps, n_features = n_features, n_layers = n_layers, d_model = d_model,
              d_inner = d_inner, n_head = n_head, d_k = d_k, d_v = d_v, dropout = dropout, last_feature_only = True)
```

That's it!
