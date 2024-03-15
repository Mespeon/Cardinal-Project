
# Cardinal Project

An all-in-one Docker image for web development and deployment.

A work in progress - expect sharp edges and rough patches.

## Before cloning the repository  
1. Install **Docker** on your local machine or cloud VM. Installation steps may vary depending on your operating system or cloud VM image. Please see https://www.docker.com/get-started/ for further information.
	
	It is also necessary to install Windows Subsystem for Linux 2 (WSL2; if you are running Windows) and enable virtualization if your CPU supports it.
2. Ensure that **Git** is installed in your local machine. If you are using a cloud VM, it is usually pre-installed already.
3. Be familiar with how containerization and Docker generally work. A general idea of how it works will go a long way to understanding how to configure this project. Please see https://www.docker.com/get-started/ for more information.
## Before building the image

1. Check if a ```volumes``` folder is inside the repository folder, or created somewhere in your VM or local machine.

	The ```volumes``` folder is where the mounted files for the Nginx, phpMyadmin, and MySQL are stored.
	
	If you intend to use a ```volumes``` folder that is outside of the repository folder, the included ```docker-compose``` file as well as the ```dockerfiles``` in each image folder should be adjusted accordingly.

	Please see Subfolders section below for more information on the included folders.
2. If you are using Windows, Docker Desktop should be up and running and is already in standby. To check if Docker is already running, run the command below:

	```docker```

	If this command returns a list of commands available for use, then Docker is already running; otherwise, it will return an error stating what is possibly wrong. If something goes wrong when starting up Docker, you may close Docker and restart it, or restart your computer.

	Cloud VMs usually have Docker accessible via CLI immediately and is exempted from this.
3. A valid ```docker-compose.yml``` file is already configured and set in place. An included example file is included and it should be used as the base file when configuring the project for your use-case. You can duplicate this and remove the ```.example``` extension, or simply create a new ```docker-compose.yml``` file and copy over the example contents. Depending on your use-case, further configuration may be required.

## Building the image
1. Open a terminal window on your local machine (or SSH into your cloud VM) and change directory to the repository's root folder where the ```docker-compose.yml``` file resides.

2. Run the command below:
	```docker compose up --build --force-recreate --detach --wait```

	Assuming that all is in place, this command should run without errors and complete successfully. Should it encounter build errors, the command execution will automatically stop and errors will be shown in the terminal.

3. If the command completes, Docker Desktop should show a couple of containers.
