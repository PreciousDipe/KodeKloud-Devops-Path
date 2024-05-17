# Linux Basics

**Linux CLI**
**Vi Editor** 
**Package Management** 
**Service Management** 


# Linux CLI

This is a command line interface for writing linux commands.
**Linux Shell**: A text based cli that helps run commands to interact with the operating system.

## Shell Types
**Bourne Shell**< sh shell> 
**C Shell**< csh or tcsh>
**Z Shell**< zsh>
**Bourne again Shell**< bash>


## Some Linux commands

    echo $SHELL - check the shell you are currently using
    echo Hi - print to screen
    ls - list files and folders
    cd my_dir1 - change directory
    pwd - present working directory
    mkdir new_directory - make Directory
    cd new_directory; mkdir www; pwd - multiple commands
    mkdir –p /tmp/asia/india/bangalore - make directory hierachy
    rm –r /tmp/my_dir1 - remove Directory
    cp –r my_dir1 /tmp/my_dir1 - copy Directory
    touch new_file.txt - create a new file (no contents)
    cat > new_file.txt - add contents to file
    cat new_file.txt - view contents of file
    cp new_file.txt copy_file.txt - copy File
    mv new_file.txt sample_file.txt - move (rename) File
    rm new_file.txt - remove (Delete) File

## User Accounts
Every linux system has a super user who is known as the rot user which can perform any task.
Root users can grant normal users access to root files/credentials

    whoami - checks user
    id - checks user id
    su username
    ssh username@192.168.1.2
    ls /root
    sudo ls /root
    
**Commands to Download Files**

    curl http://www.some-site.com/some-file.txt -O
    wget http://www.some-site.com/some-file.txt -O some-file.txt
    
**Commands to Check OS Version**

    ls /etc/*release*
    cat /etc/*release*
