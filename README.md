# Center for Agricultural Outlook

A collection of code and resources for the work of the Center for Agricultural Outlook, Korea Rural Economic Institute (KREI).

## Contents

| Item | Description |
|---|---|
| `Chronos2_tutorial.ipynb` | Chronos-2 tutorial: (1) forecasting with the pretrained parameters as they are (zero-shot), and (2) forecasting with parameters fine-tuned on cabbage prices. Uses simulated data, so it runs without any external data |
| Release `ckpt-chronos2` | Fine-tuned Chronos-2 parameters (`config.json`, `model.safetensors`). Downloaded automatically by the tutorial |

## Getting started

1. Install the packages (Python 3.10 or later)

   ```
   pip install "chronos-forecasting>=2.0" pandas numpy matplotlib
   ```

2. Open `Chronos2_tutorial.ipynb` and run the cells from the top. No GPU is needed; a two-year daily forecast takes a few seconds on CPU.
3. The base parameters (`amazon/chronos-2`) are downloaded from Hugging Face on the first run, and the fine-tuned parameters from the Release of this repository (about 0.5 GB each).

To use your own data, replace the simulation cell with `pd.read_csv(...)` and match the column names (`date`, `price`).

## Notes

- The tutorial is meant to show how the model is used. The data are a simple simulation, so the forecast accuracy itself is not meaningful.
- The fine-tuned parameters were tuned on daily cabbage prices at the Garak wholesale market (2011–2023). For other commodities, fine-tune again from the base parameters.

## Planned additions

- Forecasting with covariates (calendar, weather, etc.)
- Code for fine-tuning on your own data
- Prediction interval calibration (conformal prediction) and feature importance (SHAP)

## References

- Ansari, A. F., Shchur, O., et al. (2025). *Chronos-2: From Univariate to Universal Forecasting*. arXiv:2510.15821. https://arxiv.org/abs/2510.15821
- Model and code: https://github.com/amazon-science/chronos-forecasting, https://huggingface.co/amazon/chronos-2 (Apache-2.0)

## License

MIT License

## Contact

Minchul Park, Korea Rural Economic Institute (mcpark1352@gmail.com)
