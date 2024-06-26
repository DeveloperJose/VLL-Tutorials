# Tasks
	- DONE Look into automating with [[Ansible]]
	- TODO Install tex engine in both machines with common packages for [[LaTeX]] editing
	- DONE Set-up NVIDIA stuff so we don't need to do the weird "export" stuff for Tensorflow anymore (issue with tensorflow not us)
- # Admin Procedures @ VLL
- New user procedure
	- ```bash
	  # Add the user to the system
	  sudo adduser $USERNAME
	  
	  # Give them a directory in /data/
	  sudo mkdir /data/$USERNAME
	  
	  # Make them the owner their data directory
	  sudo chown -R $USERNAME:$USERNAME /data/$USERNAME
	  ```
- [[Docker]] management
	- https://docs.docker.com/engine/install/ubuntu/
	- ```bash
	  # Create a docker group
	  sudo groupadd docker
	  
	  # Add a user to the docker group
	  sudo usermod -aG docker $USER
	  
	  # Tell the OS to reflect the changes without rebooting
	  newgrp docker
	  
	  # Test to see if you can use docker
	  docker run hello-world
	  ```
- NVIDIA management / fixing installs on Frodo
	- ```bash
	  # Purge all NVIDIA drivers
	  sudo apt-get purge nvidia-*
	  
	  # Let Ubuntu install the recommended drivers
	  sudo ubuntu-drivers autoinstall
	  
	  # Reboot the machine
	  sudo reboot
	  ```
- # Commands Cheat Sheet
	- ```bash
	  # Check the sizes of the drives and where they are mounted
	  df -h
	  ```
	- ```bash
	  # Get the sizes of files and folders in $DIRECTORY, then sorts them, and displays the top 20
	  # --max-depth=1 makes it so it only shows one sublevel of files/directories
	  # -h makes it so it's human readable
	  # 2>/dev/null silences errors by sending them to /dev/null
	  du --max-depth=1 -h 2>/dev/null $DIRECTORY | sort -rh | head -n 20
	  ```
	- ```bash
	  # Get OS information (built-in to most OS)
	  lsb_release -a
	  
	  # Get a pretty view of the OS information
	  # REQUIRES INSTALLATION OF PACKAGE
	  # sudo apt update && sudo apt install neofetch
	  neofetch
	  ```
	- ```bash
	  # Refresh terminal shell without needing to log-out and log-in
	  exec bash
	  ```
	- ```bash
	  # Check GPU usage
	  nvidia-smi
	  
	  # Observe GPU usage in real-time
	  watch -n 0.1 nvidia-smi
	  
	  # Observe CPU and RAM usage in real-time, also Task Manager capabilities
	  htop
	  ```