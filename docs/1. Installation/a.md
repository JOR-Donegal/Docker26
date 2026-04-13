# Ubuntu 24.04 LTS

I used a fresh install of Ubuntu 24.04 Desktop. with a minimum install. I use the desktop version so I have a web browser etc. for testing.

__In whatever environment you are using, you must enable virtualization for this Ubuntu VM__.

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