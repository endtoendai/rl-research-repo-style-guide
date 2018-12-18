# Configuration (CONFIG)

```
+ .flake8
+ .travis.yml
```

## Flake8 Configuration file `.flake8`

`flake8` is a style guide enforcement tool. It is possible to configure what rules to enforce and what to ignore through the `.flake8` file in the root directory of the repository. Here is a configuration file we suggest:

```
[flake8]
exclude =
    .git,
    __pycache__,
    .ipynb_checkpoints,
max-line-length = 120
```

This enforces a maximum line length of 120 and excludes code style enforcement to files in  `.git`, `__pycache__` and `.ipynb_checkpoints` folders.

For more customization, please read the [official Flake8 documentation](http://flake8.pycqa.org/en/latest/index.html).



## TravisCI Configuration file `.travis.yml`

TravisCI is a continuous integration (CI) service that is free for open source projects. Please read [Core Concepts for Beginners](https://docs.travis-ci.com/user/for-beginners/) to learn more about CI.

Here is a simple `.travis.yml` file from the [official documentation](https://conda.io/docs/user-guide/tasks/use-conda-with-travis-ci.html):

```
language: python
python:
  - "3.6"
# command to install dependencies
install:
  - pip install -r requirements.txt -q
# command to run tests
script:
  - flake8
  - pytest
```

The `install` are run first to install necessary Python packages specified in `requirements.txt` . The `script` commands are run to test the codebase. We use `pytest`.

Similarly, here is a less-simple `.travis.yml` file using `conda`'s `environment.yml`, again from [official documentation](https://conda.io/docs/user-guide/tasks/use-conda-with-travis-ci.html):

```
language: python
python:
  # We don't actually use the Travis Python, but this keeps it organized.
  - "3.6"
install:
  - sudo apt-get update
  - wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh;
  - bash miniconda.sh -b -p $HOME/miniconda
  - export PATH="$HOME/miniconda/bin:$PATH"
  - hash -r
  - conda config --set always_yes yes --set changeps1 no
  - conda update -q conda
  # Useful for debugging any issues with conda
  - conda info -a

  # Replace dep1 dep2 ... with your dependencies
  # TODO Update environment name from test-environment
  - conda env create -f environment.yml
  - source activate test-environment

script:
  # Your test script goes here
  - flake8
  - pytest
```

