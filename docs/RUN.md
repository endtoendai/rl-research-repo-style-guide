# Training and Testing (RUN)

```
+ agents/
+ data/
+ datasets/
+ networks/
+ train_XXX.py
+ test_XXX.py
+ run.py
```

## RL agents `agents/`

This directory contains all the `Agent` classes. The `Agent` classes should have `.act()`,  `.train()`, `.test()`, `.save()`, and  `.load()` functions.



## Data `data/`

This directory contains raw data that is used for supervised learning. You may ignore this directory if your project does not use supervised learning.



## Custom Datasets `datasets/`

This directory contains custom `torch.utils.data.dataset.Dataset` classes. You may also ignore this directory if your project does not use supervised learning.



## Neural Network Modules `networks/`

This directory contains all the neural network modules that inherit `nn.Module`.  For example, a file called `dqn.py` might contain such code:

```python
import torch.nn as nn


class DQN(nn.Module):
    def __init__(self, num_inputs, num_actions):
        """
        A simple feedforward deep Q-network with two hidden layers with 128
        nodes each. Can be used with environments with feature-type states.
        """
        super().__init__()
        self.layers = nn.Sequential(
            nn.Linear(num_inputs, 128),
            nn.ReLU(),
            nn.Linear(128, 128),
            nn.ReLU(),
            nn.Linear(128, num_actions)
        )

    def forward(self, x):
        return self.layers(x)

```

