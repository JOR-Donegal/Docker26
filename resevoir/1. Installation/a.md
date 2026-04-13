# Docker Desktop

For installation, look [here](https://docs.docker.com/get-docker/) and follow the instructions for your OS or system. Use a fresh image of Ubuntu and go through the install very carefully.

In the examples below, I use a Desktop VM so I have a web browser etc. for testing. I am also using Docker Desktop and Visual Studio Code. __In whatever environment you are using, you must enable virtualization for this Ubuntu VM__.

After booting up

````
sudo apt update
sudo apt upgrade -y

# I need OpenSSH
sudo apt install openssh-server

# I need pip
sudo apt install python3-pip

# I need a simple web server
sudo apt update
pip install gunicorn
sudo apt install gunicorn
````
