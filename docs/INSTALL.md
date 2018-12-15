# Installation (INSTALL)

```
+ requirements.txt
+ environment.yml
```

The first step to reproducibility is to make the installation step smooth. To make installation smooth, you should list all the dependencies of your code. Fortunately, instead of manually updating the list, you can generate the list automatically using `pip` or `conda`.

## PyPI Environment Spec `requirements.txt`

To learn about the `requirements.txt` file, please read [this detailed documentation](https://pip.readthedocs.io/en/1.1/requirements.html).

With a simple `pip install` command, you can install all the Python packages listed in `requirements.txt`.

```
pip install -r requirements.txt
```

If you installed a new package, you can update `requirements.txt` with the `pip freeze` command:

```
pip freeze > requirements.txt
```



## Conda Environment Spec `environment.yml`

To learn about the `environment.yml` file, please read [this official conda documentation](https://conda.io/docs/user-guide/tasks/manage-environments.html).

With a simple `conda env create` command, you can create an environment and install all the Conda packages listed in `environment.yml` to that environment.

```
conda env create -f environment.yml
```

If you installed a new package, you can update `environment.yml` with the `conda env export` command:

```bash
conda env export > environment.yml
```

