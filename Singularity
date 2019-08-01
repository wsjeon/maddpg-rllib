# Header
Bootstrap: docker
From: tensorflow/tensorflow:nightly-gpu-py3

# Section
%post
    # Git
    apt-get install -y git

    # Ray rllib
    apt-get install -y libxrender1
    pip install --progress-bar off psutil
    pip install --progress-bar off -U https://s3-us-west-2.amazonaws.com/ray-wheels/latest/ray-0.8.0.dev2-cp36-cp36m-manylinux1_x86_64.whl
    pip install --progress-bar off requests

    # Multi-agent particle environments
    git clone https://github.com/wsjeon/multiagent-particle-envs.git /MPE
    cd /MPE
    pip install --progress-bar off -e .

    # Dependencies
    pip install --progress-bar off opencv-python
    pip install --progress-bar off pandas
    pip install --progress-bar off setproctitle
    pip install --progress-bar off box2d-py

%environment
    export SHELL=/bin/bash

%runscript
    exec /bin/bash "$@"
