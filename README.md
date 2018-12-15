# RL Research Repo Style Guide
**R3 Style Guide** is a comprehensive guide for a structured RL repository to accelerate research.



## Python Style Guide
### PEP8

We enforce code style with `flake8` and `autopep8`. 

However, we make one exception: we limit the number of characters per line to **120** instead of 79. We made this decision due to these reasons:

- As the neural network architecture becomes complex, the number of arguments of a single function often explodes. (Hyperparameters, networks, optimizers, etc.)
- Using shorter variable or function names makes the code unreadable.
- GitHub can show up to 120 characters per line (differs per browser, but around 120~130)

### NumPy-style Docstrings and Comments

Docstrings (`"""`) and comments (`#`) have a big impact in code quality, as it allows developers to understand the codebase quickly. Docstrings and comments have separate use:

- **Docstring** documents a module, class, or function immediately after its definition. It is a documentation for the *users*: it explains what to expect from this Python object without reading the innards.
- In contrast, **Comments** are for the *developers*. It clarifies the flow or the function of the code so that the developer who is reading the codebase can understand the inner structure.



## Repository Structure

The directories of repositories following this guide can be separated by their use into three main categories: installing, training, and logging.

```
+ agents/
+ data/
+ datasets/
+ docs/
+ networks/
+ runs/
+ saves/
+ .flake8
+ .travis.yml
+ environment.yml
+ README.md
+ requirements.txt
+ run.py
+ train_XXX.py
+ test_XXX.py
```



### Configuration (CONFIG)

```
+ .flake8
+ .travis.yml
```

These files are used to configure the `flake8` (code style enforcer) and TravisCI (continuous integration service).

Check [docs/CONFIG.md](docs/CONFIG.md) for details.

### Installation (INSTALL)

```
+ requirements.txt
+ environment.yml
```

These files are used in every computer to install necessary packages. `requirements.txt` is used for PyPI `pip` , and `environment.yml` is used for Anaconda `conda`.

Check [docs/INSTALL.md](docs/INSTALL.md) for details.

### Documentation (DOCS)

```
+ docs/
+ README.md
```

Like this `README.md`, having well-written documents explaining your repository is important. `README.md` is the first-read document of the repository. `docs/` folder may contain additional information in case `README.md` gets too big.

Check [docs/DOCS.md](docs/DOCS.md) for details.

### Training and Testing (RUN)

```
+ agents/
+ data/
+ datasets/
+ networks/
+ train_XXX.py
+ test_XXX.py
+ run.py
```

To do research, you must experiment. `train_XXX.py` trains the agent, and `test_XXX.py` tests the performance of the agent in some environment `XXX`.

Check [docs/RUN.md](docs/RUN.md) for details.

### Logging (LOG)

```
+ runs/
+ saves/
```

You will not be changing these directories yourself, but nevertheless these are important directories. Tensorboard will save the logs to `runs/`, and the parameters of the trained neural network will be saved to `saves/`

Check [docs/LOG.md](docs/LOG.md) for details.



## Examples

- [seungjaeryanlee/baselines](https://github.com/seungjaeryanlee/baselines): High-quality PyTorch 0.4.1 implementations of widely used Deep RL algorithms.

Are you using this style guide in your repository? Please create an issue so that I can add a link to your repository here!

