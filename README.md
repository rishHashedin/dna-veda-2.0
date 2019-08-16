# dna-veda-2.0

This is one of the many python layers designed as a part of ABG DNA Veda 2.0
The objectives of this layer are:
- Pick stream information from redis cache
- Read multiple streams continuously, convert them into frames and store these frames in the file system
- Push the frame information to RabbitMQ server
# Developer Guide

## Getting Started

### Prerequisites
- [python3.6](https://www.python.org/downloads/)
- [virtualenv](https://virtualenv.pypa.io/en/latest/)

### Install prerequisites

#### Python3.6

Upgrade python to python3.6 and make it as the default python:

##### Ubuntu 14.04 (Trusty), 16.04 (Xenial)
If you are using Ubuntu 14.04 or 16.04, you can use Felix Krull's deadsnakes PPA at https://launchpad.net/~deadsnakes/+archive/ubuntu/ppa:
```bash
sudo add-apt-repository ppa:deadsnakes/ppa
```
Alternatively, you can use J Fernyhough's PPA at https://launchpad.net/~jonathonf/+archive/ubuntu/python-3.6:
```bash
sudo add-apt-repository ppa:jonathonf/python-3.6
```
```bash
sudo apt-get update
sudo apt-get install python3.6
```

##### Ubuntu 16.10, 17.04
If you are using Ubuntu 16.10 or 17.04, then Python 3.6 is in the universe repository, so you can just run:
```bash
sudo apt-get update
sudo apt-get install python3.6
```

##### After installation for Ubuntu 14.04, 16.04, 16.10 and 17.04
To use python3.6 for virtualenv creation and inside virtualenv use 'python3.6'

##### Ubuntu 17.10 and 18.04 (Bionic)
Ubuntu 17.10 and 18.04 already come with Python 3.6 as default. Just use python3 to invoke it.

### Initialize the project

Keep in mind no spaces are there in the project path.

Create and activate a virtualenv:
(Make sure to activate virtual environment with python version 3.6)

```bash
virtualenv --python=python3 venv
source venv/bin/activate
```
Install dependencies:

```bash
pip3 install -r requirements/local.txt
```

## Setting up Environment Variables
Edit the environment variables in **'.env.template'** file and then **RENAME** the file to **'.env'**

NOTE: This file has already been added to .gitignore, hence it will not be pushed to your repository.
While deployment or using CI tools like travis or circle-ci, you have to take care of setting the environment variables seperately.
