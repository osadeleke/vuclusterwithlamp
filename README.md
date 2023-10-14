# Vagrant Ubuntu Cluster with LAMP Stack Deployment

Automate the deployment of a Vagrant-based Ubuntu cluster with a LAMP (Linux, Apache, MySQL, PHP) stack. This repository contains a bash script that orchestrates the entire deployment process, allowing you to set up a 'Master' and 'Slave' node with integrated LAMP stacks.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Process Overview](#process-overview)
- [Author](#author)

## Prerequisites

Before you begin, ensure you have the following prerequisites in place:

- [Vagrant](https://www.vagrantup.com/) installed on your host system.
- [VirtualBox](https://www.virtualbox.org/) or another provider supported by Vagrant.
- A Linux environment to run the deployment script.
- Basic knowledge of Vagrant and Linux systems.

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/osadeleke/vuclusterwithlamp.git
  
2. Navigate to the project directory:
   ```bash
   cd vuclusterwithlamp

4. Make sure the deployment script is executable:
   ```bash
   chmod +x deployinstall.sh

## Usage

1. Open a terminal and navigate to the project directory where the deploy.sh script is located.

2. Execute the script to start the automated deployment process:
   ```bash
   ./deployinstall.sh

### Customization
You can customize the deployment process by modifying the deploy.sh script. 

### Process Overview
#### User Management
- A user named altschool is created on the Master node
- altschool is granted root privileges on the Master Node
#### Inter-Node Communication
- SSH Key-based authentication is enabled
- The Master node (as the altschool user) can SSH into the Slave node withour requiring a password
  ```bash
  ssh slave
#### Data Management and Transfer
- On initiation, the contents of the /mnt/altschool directory (random content are created in the directory in the script to test) on the Master node are copied to /mnt/altschool/slave on the Slave node. This operation is performed using the altschool user from the Master node.

### LAMP Stack Deployment
- A LAMP stack (Linux, Apache, MySQL, PHP) is installed on both nodes.
- Apache is set to run on boot.
- MySQL is secured and initialized with a default user and password.
- New MySQL database and user are created with password enabled.
- PHP functionality with Apache is validated.

### Author
[Olusegun Adeleke](https://www.github.com/osadeleke)
