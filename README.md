# ai-lofi
AI-generated LoFi by Hannes Salzmann and Manuel Ineichen

This project is an AI-generated hommage to the musical genre of LoFi. On this website, the user is invited to "relax" to soothing LoFi-beats, produced by an audio Diffusion model.

[ai-lofi.netlify.app](link)

For the visuals, we used RunwayML's Gen-1 video diffusion model to generate a futuristic version of the iconic Study Girl animation. The original video can be seen [here](https://www.youtube.com/watch?v=jfKfPfyJRdk).

This project was made during the module COMPP by Guillaume Massol at Lucern University of Applied Sciences and Arts.

## The Model
We used HarmonAI's Dance Diffusion model, specifically the pretrained checkpoints "maestro-150k" and "jmann-small-190k".

## The Notebooks
There are two colab notebooks by HarmonAI for their Diffusion model, one to generate audio, and another one to finetune their models.

To generate audio: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Harmonai-org/sample-generator/blob/main/Dance_Diffusion.ipynb)

To finetune:[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Harmonai-org/sample-generator/blob/main/Finetune_Dance_Diffusion.ipynb)

## The Dataset
We worked with two different datasets in the course of our project:

For the first run, we used this playlist on youtube:

[Lofi Hip Hop by "the bootleg boy"](https://www.youtube.com/playlist?list=PLOzDu-MXXLliO9fBNZOQTBDddoA3FzZUo)

After some training, we realised that this playlist was not suited for out project, thus switching to this collection of Lofi beats:

[Chill Drive Lofi Hip Hop Mix by "chilli music" ](https://www.youtube.com/watch?v=nvwYWQ3Nt9g)

# The Process
As mentioned above, the project consisted of two runs.

## The first run
The first, using the playlist by "the bootleg boy", started from the pretrained checkpoint "maestro-150k".
The dataset included over 800 songs, each around 2.5 minutes long; therefore consisting of roughly 35hrs of music.
We finetuned the model for a total of 5400 steps.

The first few generations were rather underwhelming - the model generated nothing but white noise.

https://user-images.githubusercontent.com/113027541/233935835-b3dcb6d0-c63f-4360-9999-4f0a3d70f9bd.mp4

But soon enough, we were able to discern a structure in the generated samples.

https://user-images.githubusercontent.com/113027541/233936450-1cb6a60d-567d-46ec-b68c-38ba360ba4cf.mp4

After a while, we realised that our dataset was a rather loose interpretation of Lofi. It included songs with vocals and other uncharacteristic elements, which consequently appeared in our generated audio.

https://user-images.githubusercontent.com/113027541/233938417-fc0af1d8-7c2e-4c11-9ed8-3395de7a4ca0.mp4

Despite the faulty dataset, we continued training. 1000 steps later, the voices became even more prominent.

https://user-images.githubusercontent.com/113027541/233939815-e474c13c-f302-4fb4-8fc1-cae29f821ed5.mp4





