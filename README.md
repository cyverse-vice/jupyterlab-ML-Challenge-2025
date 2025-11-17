# jupyterlab-ML-Challenge-2025

The dockerfile in this repo builds an image that is meant to run in the Cyverse Discovery Environment (DE). It contains python libraries for machine learning (e.g., pytorch) and is enabled to use GPUs. The image was built for the _Harnessing the Data Revolution_ ML Challenge hosted by NEON and ESIIL. The image is currently hosted in the Cyverse harbor container registry. 

build the docker image from this repository

`docker build -f Dockerfile.ml-challenge -t harbor.cyverse.org/vice/jupyter/ml-challenge-2025:0.2 .`

<br/>

push docker image to cyverse harbor container registry

`docker push harbor.cyverse.org/vice/jupyter/ml-challenge-2025:0.2`

## Cyverse GPU Resources (as of Nov. 2025)

Cyverse DE has 26 physical GPUs (Nvidia A16s). When a user launches a GPU app, it will use 1/4 of the physical GPU with a maximum of 16 gb of RAM. 

<br/>
<br/>

## Github authentication

The GH CLI tool is installed in the image. To authenticate with your github account, open a terminal in jupyterlab and type:

`gh auth login --hostname github.com --web -p https`

Follow the prompts. It will open a browser window to authenticate with your github account. After authentication, you should be able to push changes to your github repo from the jupyterlab terminal or from the jupyterlab git widget. 

<br/>
<br/>

## Gocommands to transfer large data (>2gb) to/from Cyverse Data Store

Gocommands should already be installed to this image. To verify it is installed, open a terminal in jupyterlab and type:

`gocmd --help`

Authenicate with gocommands by typing:  
`gocmd init`

You will prompted, type in the following information:

```
iRODS Host [data.cyverse.org]:
iRODS Port [1247]:
iRODS Zone [iplant]:
iRODS Username: <your CyVerse username>
iRODS Password: <your CyVerse password>
```
More information on gocommands here https://learning.cyverse.org/ds/gocommands/

<br/>
<br/>

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

<img src="/images/cyverse_tool7.png" width=400>

<br/>
<br/>

### Create a Cyverse App 

From the Tool you created, create an interactive Cyverse App

I created an app called 'ESIIL ML Challenge 2025'

<br/>
<br/>

### How do I know if the GPU is Enabled?

After launching the Cyverse App, open a terminal in the jupyterlab and type:

`nvidia-smi -L`

The output should say the name of the GPU (e.g., NVIDIA A16)


