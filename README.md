# Pokemon Diffusion

Checkout the code: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/162p-naj-J6S-KDNzbez_0-h02gwOi3oP?usp=sharing)

Repository for the practical projecto the [*Deep Generative Diffusion Models*](https://mosi.uni-saarland.de/lectures/22_2_deep_diffusion/) Seminar at Saarland University.

We use the dataset from [pokemon-ga by Zhenye Na](https://github.com/Zhenye-Na/pokemon-gan).


## Rules ⚖️ 

### Formalities 📝 

* The goal is to implement an end-to-end diffusion model on the CelebFace dataset.
* You work alone or in groups of two.
* Plagiarism will get you expelled from the seminar and potentially exmatriculated. However, you can discuss solutions with your fellow students and take inspiration from open-source implementations (see references). 
* You can also copy&pase small code snippets if they are clearly indicated.
* We recommend Python + PyTorch for the implementation. If you want to use something else, please reach out to us. 
* Your code should run on Google Colab and normal desktop computers with minimal setup effort.
* We will invite each team to explain their code in an individual meeting. You (resp. both of you) should be able to explain the code in detail and justify design choices.
* Submit your results via e-mail to Gerrit.

### How to Pass 🎓

* To pass, you need to provide a (in a reasonable sense) technically correct implementation of a forward and backward process. You will not be judged on the visual quality of the generated images.
* In addition, you should generate animations (e.g., gifs) of the forward and backward process to illustrate what is going on during training and data generation (cf. *one_step_forward()* function).
* Comment your code extensively and assign proper names to your functions, variables, and classes. 
* Set seeds to make your code deterministic and save the final weights. 
* You should also visually verify that the forward process ends in a standard normal distribution by providing a reasonable visualization (analogously to *color_distribution_original_images.png*).
* We recommend following the denoising diffusion paradigm. When you want to use score-based or SDE methods, you can do so as well. 
* If you make very unconventional design choices, you will need to be able to justify them. 
* Do you see any problems with your implementations or room to improve? Explain in a short paragraph (can be part of the notebook). 
* You can use this notebook or use your code from scratch. 

### Notes on the Reference Implementation 💻 

* You will probably need to activate the GPU of Colab and use batched images when you want to be able to generate nice images (for passing, this is not necessary, though)
* We use a simple linear schedular and batch size of 256. 
* We predict the original image and not the noise. 
* We use a Unet, inspired by _The Annotated Diffusion Model_.
* We run at least for 1000 epochs.
* The visual quality strongly depends on the complexity of the Unet. Do not worry if your generated images look more like blobs than actual Pokomen. For passing, a minimal Unet or Autoencoder is enough. 
* Of course, you can always test other (larger) datasets to play around with.

### Bonus 🏆

For a bonus (0.3 on your final grade), you can extend the implementation in any creative way. Possibilities include:
* Smart data augmentation, extending the data set, or pre-training
* Conditioning (e.g. on the Pokemon *type*)
* Testing different network architectures, schedulers, or time-embeddings and reporting the findings.
* Using a latent diffusion approach instead of diffusion in the RGB/image space.

If you have any other idea you think is worth investigating: try it out!


### References 📚
Preliminaries 💡 
* [10 tricks for a better Google Colab experience](https://towardsdatascience.com/10-tips-for-a-better-google-colab-experience-33f8fe721b82)
* [Youtube: Deep Learning With PyTorch - Full Course (in case you need some PyTorch refreshments)](https://www.youtube.com/watch?v=c36lUUr864M&ab_channel=PatrickLoeber)
* [UvA PyTorch Tutorial](https://uvadlc-notebooks.readthedocs.io/en/latest/tutorial_notebooks/tutorial2/Introduction_to_PyTorch.html)

Diffusion 🧨
* [Tiny Diffusion Repo by tanelp (minimal example of a 2D diffusion)](https://github.com/tanelp/tiny-diffusion)
* [Youtube: Diffusion models from scratch in PyTorch](https://www.youtube.com/watch?v=a4Yfz2FxXiY&t=644s)
* [Youtube: Diffusion Models | PyTorch Implementation](https://www.youtube.com/watch?v=TBCRlnwJtZU&ab_channel=Outlier)
* [The Annotated Diffusion Model](https://huggingface.co/blog/annotated-diffusion)
* [U-Net: A PyTorch Implementation in 60 lines of code](https://amaarora.github.io/2020/09/13/unet.html)

Pokemon 🐲
* [Pokemon Images Dataset on Kaggle](https://www.kaggle.com/datasets/kvpratama/pokemon-images-dataset)
* [PokeGAN: Generating Fake Pokemon with a Generative Adversarial Network](https://blog.jovian.com/pokegan-generating-fake-pokemon-with-a-generative-adversarial-network-f540db81548d)
* [pokemon-ga by Zhenye Na (contains the dataset we are using)](https://github.com/Zhenye-Na/pokemon-gan)



## Files 📁
* `color_distribution_original_images.png`: RGB value disribution of the trainings data
* `dataset_summary.png`: Some (augmented) images from the trainings data
* `forward_animate.gif`: Animation of an (incorrect) forward process. 
* `forward_grid.png`: Imagegrid of an (incorrect) forward process. 
* `reverse_process_reference_epoch_X.gif`: Examples of the reverse process of the reference implementation after X epochs
* `color_distribution_normal_reference.png`: RGB value disribution of the trainings _after_ the forward process


<img src="https://github.com/gerritgr/pokemon_diffusion/raw/main/reverse_process_reference_epoch_002000.png" alt="Dataset Summary" width="90%">
