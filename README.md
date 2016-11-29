# Environments
Dockers and other configs for faster deployment

# List of environments

## sdcnd-term1-cpu

Basic setup for term1 of udacity self-driving car nanodegree (CPU version)

* Ubuntu 16.04 LTS
* miniconda + python 3.5
* jupyter + pandas + keras (TF and theano) + opencv

Build from Dockerfile (optional)

`docker build -t budmitr/sdcnd-term1-cpu environments/sdcnd-term1-cpu`

Start jupyter notebook and link to local folder

`docker run -d -p 8888:8888 -u dockeruser -v ~/sdcnd:/home/dockeruser/ budmitr/sdcnd-term1-cpu sh -c "jupyter notebook --ip=* --no-browser"`

Go to http://localhost:8888

## sdcnd-term1-gpu

Basic setup for term1 of udacity self-driving car nanodegree (GPU version)

* Ubuntu 14.04 LTS
* cuda 8.0, cudnn 5.1
* miniconda + python 3.5
* jupyter + pandas + keras (TF and theano) + opencv

Build from Dockerfile (optional)
`nvidia-docker build -t budmitr/sdcnd-term1-gpu environments/sdcnd-term1-gpu`

Start jupyter notebook and link to local folder
`nvidia-docker run -d -p 8888:8888 -u dockeruser -v ~/sdcnd:/home/dockeruser/ budmitr/sdcnd-term1-gpu sh -c "jupyter notebook --ip=* --no-browser"`

Go to http://localhost:8888
