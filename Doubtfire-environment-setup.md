# Doubtfire environment setup
## Step 1: Creating VM (VirtualBox)
CAUTION: You can use any kind of hypervisors
Before start creating the VM, download the Ubuntu 18.04 system image first from [here](https://releases.ubuntu.com/18.04.5/ubuntu-18.04.5-desktop-amd64.iso) or other distributors.
CAUTION: You must use Ubuntu 18.04. Otherwise, you may face unexpected errors during the "npm install" command.
CAUTION: Set the disk size to 50GB before creating the VM.
Then, use the image to install the system. 
[image:use image]
In the welcome page, choose "Install Ubuntu".
In the fourth page, do not change anything.
[image:fourth page]
CAUTION: Do not use minimal installation.

## Step 2: Installing Guest Additions [Optional]
Open a terminal and execute the following commands.
- sudo apt-get update
- sudo apt-get install build-essential gcc make perl dkms
- reboot

After the system restarted, insert guest addtions image and install the softwares.
[image: guest addtions]
After the installation, reboot the system.

## Step 3: Installing GIT and VS Code
CAUTION: You can use any kind of IDEs.
Open a terminal and execute the following commands.
- sudo apt install git
- git --version

If you see a output with "git version x.xx.x", then you successfully installed it.
Download the VS Code installer from [here.](https://code.visualstudio.com/docs/?dv=linux64_deb)
Execute the installer inside the VM.
After the installation of VS Code, open it and install "Live Share Extension Pack".
[image: liveshare]

## Step 4: Fork Doubtfire Repositories and Clone Them to VM
Open both links:
- [Doubtfire-web](https://github.com/doubtfire-lms/doubtfire-web)
- [Doubtfire-api](https://github.com/doubtfire-lms/doubtfire-api)

Click the fork button at the upper right side of both websites.
[image: fork]
Then, execute the following commands.
- cd ~/Desktop/
- git clone https://github.com/[YOUR GITHUB ACCOUNT NAME]/doubtfire-api
- git clone https://github.com/[YOUR GITHUB ACCOUNT NAME]/doubtfire-web
- cd doubtfire-api/
- ./setup.sh

CAUTION: SWAP the content inside [] with your github account name. e.g, erickao5858 which is my account name.
After installing the dependencies, execute the following command to verify whether the backend project works properly.
- bundle exec rails s

If the output looks exactly the same way with the image below, move to the frontend project.
[image: backend]
Keep the backend terminal alives all the time because you need it handling data.
Open another terminal and execute the following commands.
- cd ~/Desktop/doubtfire-web/
- ./setup.sh

After installing the dependencies, execute the following command to verify whether the frontend project works properly.
- npm start

If the output looks exactly the same way with the image below, then it's finished.
[image: frontend]

Finally, open the firefox broswer and go this website: https://localhost:4200/.
Type in username "acain" and password "password".
If you see it does functioning, you can take a screenshot as an evidence and post it in the team channel.
[image: screenshot]
# Congratulation!
