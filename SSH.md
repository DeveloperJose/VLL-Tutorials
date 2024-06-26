- SSH (Github)
  id:: 66692e0a-b4b3-4185-8f28-b5407fe4161a
	- This will allow you to push changes to your repositories (securely)
	  logseq.order-list-type:: number
	- Generate an SSH key in the server with
	  logseq.order-list-type:: number
		- logseq.order-list-type:: number
		  ```
		  ssh-keygen
		  ```
	- Get public key and copy to clipboard
	  logseq.order-list-type:: number
		- logseq.order-list-type:: number
		  ```
		  cat ~/.ssh/id_rsa.pub
		  ```
	- Github->Settings->SSH and GPG keys->New SSH key
	  logseq.order-list-type:: number
	  id:: 66692ec4-3f2c-45e7-bc97-72c27e51d503
	- logseq.order-list-type:: number
	  ```
	  git clone $SSH_URL
	  ```
- SSH (Windows)
  id:: 66692e0a-2eff-4187-b768-c7acc4334bba
	- This will allow you to connect to the machine without a password (securely)
	  logseq.order-list-type:: number
	- Open PowerShell in your local computer and generate an SSH key
	  logseq.order-list-type:: number
		- logseq.order-list-type:: number
		  ```
		  ssh-keygen
		  ```
	- Copy "~/.ssh/id_rsa.pub" into the server as "~/.ssh/authorized_keys"
	  logseq.order-list-type:: number
		- You can have multiple, like "authorized_keys2" and so on
		  logseq.order-list-type:: number