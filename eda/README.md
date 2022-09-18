# Flood Risk EDA
---

## Enviroment Instructions

The Dockerfile builds a GeoPandas enviroment and launches gitlab. When in the eda directory on the command line
run the following docker build commands

'docker build -t w210-eda-env .'

The initial build will take some time. When the build has completed run the following command. Remember to
replace the <local_directory_here> with the host directory you want to import into the workspace.

'docker run -it --rm -p 8888:8888 --volume /home/dan/Documents/w210:/workspace w210-eda-env'
