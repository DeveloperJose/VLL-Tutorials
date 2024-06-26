# Useful URLs
	- https://hub.docker.com/r/pytorch/pytorch/
	- https://hub.docker.com/r/tensorflow/tensorflow
	- https://hub.docker.com/r/nvidia/cuda
	- https://hub.docker.com/_/python
	- https://hub.docker.com/_/debian
	- https://hub.docker.com/_/alpine
	- https://hub.docker.com/_/ubuntu
- # Base OS Images
	- Most images in Docker Hub will derive from one of these base OS images
	- Alpine Linux
		- Very lightweight (5MB)
		- Uses "apk" package manager, [packages here](https://pkgs.alpinelinux.org/packages) but fewer than Debian/Ubuntu's "apt"
	- Debian
		- Parent of Ubuntu
		- Different versions, including "slim" versions
		- Uses "apt" package manager
	- Ubuntu
		- OS for all our server machines
		- Heavier images (75MBs) but contains more tools and libraries
		- [Why Use Ubuntu as a Docker Base Image When Alpine Exists? | JFrog](https://jfrog.com/devops-tools/article/why-use-ubuntu-as-a-docker-base-image-when-alpine-exists/)
- # Empty Dockerfile
	- ```
	  FROM $IMAGE
	  
	  RUN ...
	  
	  COPY ... ...
	  
	  
	  WORKDIR /app
	  
	  ENTRYPOINT [ "python" ]
	  ```
- # Deep Learning
	- Install [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html), requires **sudo**
	- Run [[Tensorflow]] image
	- ```
	  docker run -it --rm --runtime=nvidia tensorflow/tensorflow:latest-gpu python -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
	  
	  docker run -it --rm --runtime=nvidia tensorflow/tensorflow:latest-gpu nvidia-smi
	  ```
	- Run [[PyTorch]] image
	- ```
	  docker run -it --rm --runtime=nvidia pytorch/pytorch:2.3.1-cuda12.1-cudnn8-devel nvidia-smi
	  
	  docker run -it --rm --runtime=nvidia pytorch/pytorch:2.3.1-cuda12.1-cudnn8-devel python -c "import torch; print(torch.cuda.is_available())"
	  ```
-