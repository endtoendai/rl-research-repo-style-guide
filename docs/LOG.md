# Logging (LOG)

```
+ runs/
+ saves/
```

## Tensorboard Log `runs/`

Tensorboard is a great visualization tool. Although it was designed for TensorFlow, you can also use it with PyTorch using [TensorboardX](https://github.com/lanpa/tensorboardX). By default, Tensorboard will use the `runs/` folder as its log directory. We leave it as is.



## PyTorch Checkpoints `saves/`

After training your agent, you should save your neural network parameters so that you can either 1) test your agent in various seeds or 2) continue training your neural network at a later date. You will use the `saves/` directory for this purpose.

