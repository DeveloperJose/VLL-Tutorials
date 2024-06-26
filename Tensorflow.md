- Install (pip), following the [website instructions](https://www.tensorflow.org/install)
	- python -m pip install tensorflow[and-cuda]
	- Tensorflow 2.14 is the first to include [and-cuda]
	- Might require you to run this or add it to "~/.bashrc" or https://github.com/sgkouzias/docs/blob/patch-1/site/en/install/pip.md
		- ```bash
		  export CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))
		  export LD_LIBRARY_PATH=${CUDNN_PATH}/lib
		  ```
		- ```bash
		  pushd $(dirname $(python -c 'print(__import__("tensorflow").__file__)'))
		  ln -svf ../nvidia/*/lib/*.so* .
		  popd
		  ```
- Install (conda), following [anaconda tutorial](https://docs.anaconda.com/free/working-with-conda/applications/tensorflow/) and looking at [the compatibility list](https://www.tensorflow.org/install/source#gpu)
  id:: 6669436a-f68e-4d2a-a670-4aeba7a998ca
	- Can only install up to Tensorflow 2.4.1 with this, Python compatible between 3.6 and 3.8
	- ```
	  conda install tensorflow-gpu
	  ```
- To test
	- id:: 66694281-4ec0-4667-9701-a25cf6f8a8fa
	  ```
	  python -c "import tensorflow as tf; print(len(tf.config.list_physical_devices('GPU')))"
	  ```