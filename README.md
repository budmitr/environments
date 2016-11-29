# Environments
Dockers and other configs for faster deployment

# List of environments

## sdcnd-term1-cpu

Basic setup for term1 of udacity self-driving car nanodegree (CPU version)

* Ubuntu 16.04 LTS
* miniconda
* jupyter + pandas + keras (TF and theano) + opencv

Build image from Dockerfile
`docker build -t sdcnd-term1-cpu ./sdcnd-term1-cpu`

Start jupyter notebook
`docker run -p 8888:8888 -u dockeruser sdcnd-term1-cpu sh -c "jupyter notebook --ip=* --no-browser"`

Start jupyter notebook and link to local folder
`docker run -d -p 8888:8888 -u dockeruser -v ~/sdcnd:/home/dockeruser/ sdcnd-term1-cpu sh -c "jupyter notebook --ip=* --no-browser"`

Go to http://localhost:8888

## sdcnd-term1-gpu

Basic setup for term1 of udacity self-driving car nanodegree (GPU version)

* Ubuntu 14.04 LTS
* miniconda
* jupyter + pandas + keras (TF and theano) + opencv

Build image from Dockerfile
`nvidia-docker build -t sdcnd-term1-gpu ./sdcnd-term1-gpu`

Start jupyter notebook
`nvidia-docker run -p 8888:8888 -u dockeruser sdcnd-term1-gpu sh -c "jupyter notebook --ip=* --no-browser"`

Start jupyter notebook and link to local folder
`nvidia-docker run -d -p 8888:8888 -u dockeruser -v ~/sdcnd:/home/dockeruser/ sdcnd-term1-gpu sh -c "jupyter notebook --ip=* --no-browser"`

Go to http://localhost:8888
