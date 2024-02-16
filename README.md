# BH-24-2Y
This is an application of a conditional Variational Autoencoder similar to the problem of "2 Bird 1 Neural Network"

The objective is to use a generative model to find new functions (x0 & x1) that can fit certain functions, like cos(4 x0 + 8 x1)

The obvious choices were to use a CVAE or a GAN, I chose to go with a CVAE, since and if time permits experiment with a GAN.

Approaching the challenge in a structured challenge, I decided to first set up my hyperparameter tuning for the already given model, which would be useful in the future with any changes. 

While setting up optuna I encountered some errors.

After correctly setting up my optuna, I got these results
![image](https://github.com/Mehul0x/BH-24-2Y/assets/146676085/e662f363-74fc-4ab6-a7c7-ee4986fe03df)
![image](https://github.com/Mehul0x/BH-24-2Y/assets/146676085/f7aa67d8-dadd-4a31-bb28-329912db442f)

After this, I varied the parameters of the model and then optimized its hyperparameter, through a lot of iterations I got the best result
![image](https://github.com/Mehul0x/BH-24-2Y/assets/146676085/a0bcf9e6-a19e-4e4a-8a29-29c4f3db0d9c)
![image](https://github.com/Mehul0x/BH-24-2Y/assets/146676085/2ee27a0f-6cf3-460a-9e81-814455393f7a)

This was the test loss on this iteration
![image](https://github.com/Mehul0x/BH-24-2Y/assets/146676085/e31aec06-5755-4b02-8497-93b2924ed703)

The same architecture with different hyperparameters performed as
![image](https://github.com/Mehul0x/BH-24-2Y/assets/146676085/4bd3aaf6-9da7-4c63-a73f-fa9f62a43441)

I tried replacing a convolutional layer with a linear layer but the results had a significant drop, so I decided to add other convolution layers instead, I encountered some errors and time didn't permit me to fix them.

For the number of epochs, I noticed that increasing them beyond 40-45 was not affecting the y_loss, so I only used 50 epochs for each training.
1 weird thing I noticed was that my KLD loss was -ve in some epochs even though theoretically it wasn't possible
