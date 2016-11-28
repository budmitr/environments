# Environments
Dockers and other configs for faster deployment

# List of environments

## basic-deeplearning-cpu

* Ubuntu 16.04 LTS
* miniconda
* jupyter + pandas + keras (TF and theano)

Start jupyter notebook
`docker run -p 8888:8888 -u dockeruser basic-deeplearning-cpu jupyter notebook --ip=0.0.0.0`

Go to http://localhost:8888
