# Flood Risk EDA
---

## Enviroment Instructions

The Dockerfile builds a GeoPandas environment and launches gitlab. When in the eda directory on the command line
run the following docker build commands

### AWS Allocation
Smallest recommended AWS environment r6a.8xlarge due to file size and recommend building with the Ubuntu Server 22.04 LTS AMI

### AWS Security group

- Confirm all outbound calls are allowed
- Confirm SSH is allowed
- Open port 8888 to allow jupiter lab access

### Storage

- Recommend starting out with 500 gigs of storage

### Setting up Instance

Run apt-get update and apt-get upgrade and reboot instance to update base AMI.

Install docker per install instructions here: https://docs.docker.com/engine/install/ubuntu/

Install git

Git clone repo to Instance

Navigate to /home/ubuntu/flood-risk/eda and copy Dockerfile to /home/ubuntu

Build the docker image with the following command

'docker build -t w210-eda-env .'

The initial build will take some time. When the build has completed run the following command.

Launch the environment with the following command.Replace the <local_directory_here> with the host directory you want to import into the workspace.

'docker run -it --rm -p 8888:8888 --volume <local_directory_here>:/workspace w210-eda-env'

When the environment launches it will provide a jupyter lab link. This link will have to be modified as it does not take remote access into consideration.

http://127.0.0.1:8888/lab?token=f8a0c890ee31ec4ff3b7eefd011068183424598b63dc4892

Replace the 127.0.0.1 IP adress with the public IP adress of the EC2 instance and paste in browser of your choice.
