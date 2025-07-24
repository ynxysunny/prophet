# Stepwise-Prophet: Automatic Forecasting Procedure with Stepwise Trend

Stepwise-Prophet is a fork of Facebook's Prophet that adds support for stepwise (piecewise flat) trend modeling. This extends the original Prophet forecasting procedure to handle time series with sudden level changes while maintaining all original functionality including yearly, weekly, and daily seasonality, plus holiday effects.

This package is based on Prophet, which is [open source software](https://code.facebook.com/projects/>)  released by [Facebook's Core Data Science team ](https://research.fb.com/category/data-science/).

Full documentation and examples available at the homepage: https://facebook.github.io/prophet/

## Important links

- HTML documentation: https://facebook.github.io/prophet/docs/quick_start.html
- Issue tracker: https://github.com/facebook/prophet/issues
- Source code repository: https://github.com/facebook/prophet
- Implementation of Prophet in R: https://cran.r-project.org/package=prophet

## Other forecasting packages

- Rob Hyndman's [forecast package](http://robjhyndman.com/software/forecast/)
- [Statsmodels](http://statsmodels.sourceforge.net/)

## Installation - PyPI release

See [Installation in Python - PyPI release](https://github.com/facebook/prophet#installation-in-python---pypi-release)

## Installation - Development version

See [Installation in Python - Development version](https://github.com/facebook/prophet#installation-in-python---development-version)

### Installation using Docker and docker-compose (via Makefile)

Simply type `make build` and if everything is fine you should be able to `make shell` or alternative jump directly to `make py-shell`.

To run the tests, inside the container `cd python/stepwise_prophet` and then `python -m pytest stepwise_prophet/tests/`

### Example usage

```python
  >>> from stepwise_prophet import Prophet
  >>> m = Prophet(growth='stepwise')  # Use stepwise trend modeling
  >>> m.fit(df)  # df is a pandas.DataFrame with 'y' and 'ds' columns
  >>> future = m.make_future_dataframe(periods=365)
  >>> m.predict(future)
```
