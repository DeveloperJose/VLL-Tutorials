- To train with one or some GPUs in the same PC, call the code like this
	- ```
	  CUDA_VISIBLE_DEVICES=0 python train.py
	  ```
	- OR
	  
	  ```
	  CUDA_VISIBLE_DEVICES=0,1 python train.py
	  ```
	- OR set the GPU device in your Python code, there are tutorials for that
- To train with multiple GPUs or CPU+GPU in the same PC, simply follow the tutorial for your framework
	- [PyTorch DataParallel](https://pytorch.org/tutorials/beginner/former_torchies/parallelism_tutorial.html)
- To train with GPUs in different PCs
	- You need to have the dataset somewhere both PCs can access like Amazon S3 or have a copy of the dataset in each PC
	- The machines must be in the same network or able to communicate with each other
	- You need to use a library that can support this
		- [PyTorch-Lightning](https://lightning.ai/docs/pytorch/stable/accelerators/gpu_intermediate.html)
	- You need to set-up your code to support this
		- Usually just means one Python training script which takes parameters from the command-line so the library can call that file with different parts of the dataset, parameters, etc