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
The first run, using the playlist by "the bootleg boy", started from the pretrained checkpoint "maestro-150k".
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

After 5400 steps in total, we decided to abort training on this dataset. The stylistic inconsistency of the used playlist lead to incoherent outputs that seemed to far away from actual Lofi.

https://user-images.githubusercontent.com/113027541/233952930-d2ae7ff4-7954-4fd4-8960-90a07a093c89.mp4

## The second run
The second run, using the playlist by "chilli music", started from the checkpoint "jmann-small-190k". This dataset is smaller than the first, consisting of roughly 12hrs of Lofi. The training ran for roughly 8500 steps, producing much better results than the first run. There are two main reasons for this:

1. The smaller size of the dataset allowed us to do better preprocessing. We adjusted the sample rate of the training data to 48'000 to match the pretrained model. On top of that, we were able to chunk the audio into smaller samples for training. 

2. The dataset is more consistent in it's style. There are no tracks that include vocals or any other uncharacteristic sounds.

https://user-images.githubusercontent.com/113027541/233964821-c90b8cbe-bcfd-4088-b54b-35bd4d3a76f9.mp4

The outputs of this run were much more clear and consistent from the beginning.

https://user-images.githubusercontent.com/113027541/233989856-ef00e1d2-a14d-46d3-9367-dedf85cc78f5.mp4

After 5000 steps, the characteristic elements of Lofi started to take over.

https://user-images.githubusercontent.com/113027541/233992029-10f87356-52e9-4e11-aef8-48f625991289.mp4

Shortly after 6000 steps, the generated audio didn't seem to get any better. The graph below shows that the training loss increased greatly after the 196k mark (red).

![run2_a](https://user-images.githubusercontent.com/113027541/233996955-dc236b99-f0fc-4048-ba79-e4d3a56fa9c0.png)

After a few unsuccessful retries from older checkpoints, we decided to stop training. Even though a few runs managed to keep the loss low (green), the output did not sound much better than at 6000 steps.
