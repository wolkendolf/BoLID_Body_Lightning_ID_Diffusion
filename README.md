# Full-length human image generation using diffusion models.

**Author:** Kazachkov Daniil <br>
**Supervisor:** Filatov Andrew

## Problem Statement
Our main goal is to expand the scope of diffusion models in generating high-quality images. We test the hypothesis that the approaches in [PuLID](https://github.com/ToTheBeginning/PuLID), [InstantID](https://instantid.github.io/), and [IP-Adapter] (https://ip-adapter.github.io/) apply not only to facial avatars, but also to full-body avatars. We achieve this by modifying the dataset and the encoder that takes the user's reference image as input.
A separate part of the experiment is an attempt to find the best method for extracting the human body (BodyID) from an image. 

## Train baseline model
To do this, install all dependencies from [IP-Adapter](https://ip-adapter.github.io/), replace `tutorial_train_plus.py` with the corresponding file `./model_train/tutorial_train_plus.py`. The script is run by executing the `train.sh` script, which must first be moved to the `IP-Adapter` directory.
