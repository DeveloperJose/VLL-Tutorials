- To install, follow the [website instructions](https://pytorch.org/)
	- conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
- To test
	- ```
	  python -c "import torch; print(torch.cuda.is_available())"
	  ```