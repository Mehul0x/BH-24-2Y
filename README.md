# BH-24-2Y
This is an application of a conditional Variational Autoencoder similar to the problem of "2 Bird 1 Neural Network"

The objective is to use a generative model to find new functions (x0 & x1) that can fit certain functions, like cos(4 x0 + 8 x1)

The CVAE had the following hyperparameters "latent dimension, learning rate, batch size, beta, wx, wy"
I chose to use optuna to optimize these hyperparameters.

A study is created with an objective with the goal of minimzing the objective, in this case, the total loss returned by the CVAE, represented as 
total_loss = (beta * KLD + wx * x_loss + wy * y_loss).mean()
Such a loss function is used because we want to minimize both the Kullback–Leibler divergence loss and the reconstructional loss to make sure the data is spread out in the latent space and segregated.
