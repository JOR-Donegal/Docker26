# Visual Studio Code

I installed Visual Studio Code (VSC) using instructions from [here](https://code.visualstudio.com/docs/setup/linux). I downloaded the .deb file and installed. The commands were

````
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg

sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg

sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

rm -f packages.microsoft.gpg

sudo apt install apt-transport-https
sudo apt update
sudo apt install code

````
I add extensions for Docker and Python (you should know how to do this!!). 

Press [CTRL][SHIFT][P] for the command palette, Type Python and select Python Interpreter. Use the default or recommended version.

Finally, I create a folder called Docker in my home directory. Each example I do will be in a subdirectory here.