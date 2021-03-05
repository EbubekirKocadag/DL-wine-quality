# DL-wine-quality

## What

On this repository, with wine dataset, we will try to understand how a neurol network is created and how it's work. 

## Why

Our main objectif in this exercise was to learn how to create an neurol network, how to improve our model.

## When

During BeCode training. The exercise took around 4 days.

## How

In this project, we used pyTorch. To install it, first we create an environnement in code and install with:
`conda create -n pytorch python=3.7 pandas numpy notebook ipykernel pytorch=1.7 torchvision torchaudio cudatoolkit=11.0 -c pytorch`
The reason why we used this way for installing pytorch is because we have a mac and other ways didn't work. If you have another OS you can check in [this website](https://pytorch.org/get-started/locally/)how to install.

We also install ray.tune to optimize our hyperparameter. You just need to write this code in your terminal `pip install 'ray[tune]'`.

Once everything is ready, first thing that we done, is to understand our dataset. After that, we creat a baseline neral network (neural network as basic as possible). We had an accuracy of ~50% in both train and test set. After that, in the second notebook, we creat a ray.tune to find the best hyperparameters but we had a lot of issues because of our computer performance. Anyway after some tries, we succeded to find a set of hyperparameters (that's a thing probably to improve). Finally, we got these hyperparameters:
- learning_rate: 0.001
- batch_size: 100
- epochs: 200
- hidden_neurones: 200
- nb_hidden_layers: 6
- activation_input_layers: CELU
- activation_hidden_layers: SiLU
- activation_output_layers: Softmax

With an unpsampling, we have 95% for test and train set.

The thing that influence the most our accuracy is the upsampling. We passed from 50% to 70% just with an upsampling, the reason for that is the number of value that we have for quality equal to 9 (only 5) and 3 (30). Changing input layers's activation function had a big influence too (+ ~10%). Of course, we have a lot of thing to do but since we didn't have enough time we will stop here.

## Who

[Ebubekir Kocadag](https://github.com/EbubekirKocadag), junior AI developer

## Pending things to do

Since, we didn't have enough time we couldn't change a lot things in our dataset, so maybe we can divide the dataset in two. One with red wine and the other with white wine. We can also redo another ray.tune with bigger value. 
