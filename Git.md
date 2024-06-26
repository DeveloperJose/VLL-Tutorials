- Getting started
	- Generate an ssh-key to authenticate to Github with
	- ```bash 
	  ssh-keygen
	  ```
	- Create an account on Github and add your public key to your Settings
	- ```bash
	  cat ~/.ssh/id_rsa.pub
	  
	  OR
	  
	  cat ~/.ssh/id_ed25519.pub
	  ```
	- Configure your git
	- ```bash
	  git config --global user.name "Jose G. Perez"
	  git config --global user.email "josegperez@mail.com"
	  ```
- Useful commands cheat sheet
	- ```bash
	  git clone
	  git status
	  git log
	  git add ...
	  git commit -m "message"
	  git push
	  ```