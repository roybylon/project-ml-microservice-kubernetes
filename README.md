[![CircleCI](https://dl.circleci.com/status-badge/img/gh/roybylon/project-ml-microservice-kubernetes/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/roybylon/project-ml-microservice-kubernetes/tree/main)

## Project Overview

In this project, I appllied the skills i have acquired in this course to operationalize a Machine Learning Microservice API. 

Given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

**The final implementation of the project showcased my abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
```
    minikube start
    kubectl get pod
```

* Create Flask app in Container
```
    docker run -p 8080:80 roybylon/ml-api
```
* Run via kubectl
```
    kubectl run ml-api --image=$dockerpath --port=80
    kubectl port-forward roybylon/ml-api 8080:80
```    
 

## File directories

.circleci/config.yml - circleci configuration

model_data -  housing prices in Boston area

output_files/docker_out.txt - docker log outputs

output_files/kubernetes_out.txt - kubernetes log outputs

app.py - flask app API endpoint with routes to get house prices in Boston

Dockerfile - Docker configuration file

make_prediction.sh - script to log predictions endpoint output

Makefile - The Makefile includes instructions on environment setup and lint tests

requirements.txt - python dependencies for this project

run_docker.sh - shell script to build docker image and run it

run_kubernetes.sh - shell script to run the Docker Hub container with kubernetes

upload_docker.sh - shell script to upload local docker build image to docker hub (online repository)

commands.txt - exported list of all commands that was executed in the cause of the project

screeshots - the project contains two screenshots showing the AWS cloud9 workspace while the project was ongoing

