# :question: FAQ

A list of frequently asked questions

## :wrench: Virtual Environment

## :interrobang: SSL Error when using [`fetch_openml`](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_openml.html)

Add the following two lines of code at the top of the Python script.

```python
import ssl
ssl._create_default_https_context = ssl._create_unverified_context
```

> See [reference](https://stackoverflow.com/a/69120255) from StackOverflow.
