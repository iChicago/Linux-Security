# Linux-Security
Some useful notes taken while studying this topic on Udacity

## Super User
- It is very common to disable the ability to remotly log in as **root**.
- What if we want to use root commands? 
  - we can create another user and give it **root access**
- It is not recommended to use *SU* commands. (You may mess up your system)

## Package Source List
- All available pakege sources are listed in ```cat /etc/apt/sources.list```
- Update them ```sudo apt-get update```
  - This will update the package list (Not updating all applications)
- Upgrade the installed packages ```sudo apt-get upgrade```
- Remove unused packages ```sudo apt-get``` autoremove

## Finger
- To print all users thar are currently logged in the system ```finger```
- To see more info about particular user ```finger yourUserNmae```
- This is a very important file on your system! It's used to keep track of all users on the system. ```cat /etc/passwd```
  - username:password:UID:GID:UID info:home directory:command/shell

## User Management
- Create user ```sudo adduser student```
  - **This user doesn't have root permissions**
- Connect to the new user remotely ```ssh student@120.0.0.1 -p 2222```

## Sudoers file
- This file shows all users that have **Sudo** permisions ```cat /etc/sudoers```
  - New sudo users are listed under this file ```sudo ls /etc/sudoers.d```
  - Each sudo user have a file in **sudoers.d** directory

## Giving a Sudo Permission
- Copy a sudo user's file (**vagrant**) and rename it to the new users's name (**student**)
  - ```sudo cp /etc/sudoers.d/vagrant /etc/sudoers.d/student```
- Go inside the file **student** and run the command 
  - ```sudo nano /etc/sudoers.d/student```
  - rename **vagrant** to **student** 
  - save the file
  
## Ressiting Password
- To force a user to hcange his password next time when they log in ```sudo passwd -e student```
  - **-e** means **Expire**

## Generating Key Pairs
- To generate public and private keys use ```ssh-key-gen```
  - Enter the location of resulting pair 
  - You will get **two** files 
    - private key **fileName**
    - public key **fileName.pub** 
      - we will store this file in our server
- Supported Key Types
  - DSA
  - ECDSA
  - ED12219
  - **RSA** is the defualut
    
