- virtualenv + pip
	- Built into Python
	- Just needs "requirements.txt"
	- Requires admin to install specific Python versions and the virtualenv module for that version
- [conda](https://docs.anaconda.com/free/miniconda/miniconda-install/)
  id:: 666934c5-b182-4a00-99aa-fb87d1019199
	- Manages "environments" for you
	- Can install specific Python versions for each environment
	- Easy to use
	- A lot of support and resources dedicated to getting common frameworks installed with GPU/CUDA support
		- Conda channels have specific builds for common packages
	- Can export and import environments to other conda users as "environment.yml" or to "requirements.txt"
	- Can still use pip when needed
	- Slow dependency resolution at times
		- Can be sped up by using a tool called "mamba"
	- ```
	  conda create --name myenv python=3.10
	  conda activate myenv
	  
	  
	  conda env list
	  conda env remove --name myenv
	  ```
	- Install:
		- ```
		  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
		  sh Miniconda3-latest-Linux-x86_64.sh
		  ```
- [pyenv](https://github.com/pyenv/pyenv)
	- Manages Python versions for you, that's it
	- ```
	  pyenv install 3.10
	  pyenv global 3.10
	  pyenv local 3.10
	  ```
- [poetry](https://python-poetry.org/docs/)
	- Manages virtualenv for you
	- Does not install Python versions
	- Faster dependency resolver than conda
	- Easily reproducible as lock file contains your specific dependencies so anyone else that runs "poetry install" runs the same packages and versions
	- Puts dependencies in "pyproject.toml" which is also used to put other configurations for other tools, unifying everything
	- ```
	  poetry init
	  poetry add $package
	  poetry add --group dev $package
	  poetry install
	  poetry run python main.py
	  ```
- Docker
	- Pick a base image (usually an OS), then write "Dockerfile" on how to prepare your container
	- Runs the same anywhere the docker engine is installed
	- Not just for Python packages, but also for any other tools/libraries/software