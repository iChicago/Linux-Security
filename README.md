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

