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

![150031](audio/run_1/150031.wav)
