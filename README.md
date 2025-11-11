# jupyterlab-ML-Challenge-2025

The dockerfile in this repo builds an image that is meant to run in the Cyverse Discovery Environment (DE). It contains python libraries for machine learning (e.g., pytorch) and is enabled to use GPUs. The image was built for the _Harnessing the Data Revolution_ ML Challenge hosted by NEON and ESIIL. The image is currently hosted in the Cyverse harbor container registry. 

build the docker image from this repository

`docker build -f Dockerfile.ml-challenge -t harbor.cyverse.org/vice/jupyter/ml-challenge-2025:0.1 .`

<br/>

push docker image to cyverse harbor container registry

`docker push harbor.cyverse.org/vice/jupyter/ml-challenge-2025:0.1`

## Cyverse GPU Resources (as of Nov. 2025)




## Create Cyverse DE Tool

Go to the Cyverse DE and go to 'Tools'

<img src="https://github.com/cyverse-vice/jupyterlab-minimal/blob/main/images/cyverse_tool.png" width=600>

<br/>

<img src="https://github.com/cyverse-vice/jupyterlab-minimal/blob/main/images/cyverse_tool2.png" width=200>

<br/>

Fill out the tool information as such

<img src="https://github.com/cyverse-vice/jupyterlab-minimal/blob/main/images/cyverse_tool3.png" width=400>

<img src="https://github.com/cyverse-vice/jupyterlab-minimal/blob/main/images/cyverse_tool4.png" width=400>

<img src="https://github.com/cyverse-vice/jupyterlab-minimal/blob/main/images/cyverse_tool5.png" width=400>

<br/>

Go to the 'Tools' under the Admin. You need admin privaledges for this to be visible. 

<img src="https://github.com/cyverse-vice/jupyterlab-minimal/blob/main/images/cyverse_tool6.png" width=400>

### Create a Cyverse App 

From the Tool you created, create an interactive Cyverse App

I created an app called 'ESIIL ML Challenge 2025'

### How do I know if the GPU is Enabled?

After launching the Cyverse App, open a terminal in the jupyterlab and type:

`nvidia-smi -L`

The output should say the name of the GPU (e.g., NVIDIA A16)
