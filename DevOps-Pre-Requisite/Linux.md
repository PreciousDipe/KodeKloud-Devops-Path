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

# Package Manager
They help istall many packages on the linux systems.
**CentOS** uses RPM < RedHat Package Manager>
**YUM** is a high level package manager that uses rpm underneath, it also helps install all dependecies associated with a package
**Every OS comes installed with its own repository where you can install softwar and tools**

## Some Commands

    rpm –i telnet.rpm       Install Package
    
    rpm –e telnet.rpm       Uninstall Package
    
    rpm –q telnet.rpm       Query Package
    
    yum install ansible     Install Package
    
    yum list ansible
    
    yum remove ansible
    
    yum --showduplicates list ansible
    
    yum install ansible-2.4.2.0


# Vi Editor
It has **2 modes**
**Command mode** This is the mode you enter when you one a file with this editor
**Insert mode** This mode is used to write contents to a file. To enter this mode press **i** and to go back to the command mode press **ESC**

## Some Vi Commands

    delete                x                      dd
    copy and paste        yy                      p
    scrollup/down         ctrl+u                ctrl+d
    command               :
    save                  :w                    :w filename
    quit                  :q
    save+quit             :wq
    find                  /OF            n-move cursor
    u                     undo change
    ctrl+r                redo change


# Services
This helps configure softwares to run in the background and keep running automatically
	
> The sytemctl command line is used to manage the systemd service. 
> The **systemd service** is configured using a systend unit file which are located at  **etc/systend/systempath**
> To automatically run your applications use the **WantedBy Service** which will make it run after a particular service at bootup

## Some Services Commands

    systemctl status my_app
    systemctl daemon-reload
    systemctl start my_app
    systemctl stop my_app
    systemctl enable my_app

    /etc/systemd/system
    my_app.service
    ExecStart= /usr/bin/python3 /opt/code/my_app.py
    
    [Install]
    WantedBy=multi-user.target

# Networking

> To connect 2 networks together you need a **switch** 
> A **switch** can only enable communication in a network A **router** helps connect 2 networks together
> By default in linux packets are not forwarded for security purposes
> A gateway is like a network door that takes you to the correct destination< ip>

## Some Commands

    ip link
    ping 192.168.1.11
    ip addr
    ip addr add 192.168.2.0/24 dev eth0
    route
    ip route add 192.168.2.0/24 via 192.168.1.1
    cat /proc/sys/net/ipv4/ip_forward
    echo 1 > /proc/sys/net/ipv4/ip_forward

## DNS
A **DNS** is used to resolve the hostname of an address into the server.

**Record Types** 
- A   -----------Storing as IP to hostname 
- AAAA ----------------------Storing as IPv6 to hostname 
- CNAME -----------------mapping one name to another

```mermaid
graph LR
A[www.google.com]-- Root --> B(.)
A -- Top Level Domain Name --> C(.com)
A -- domain name --> D(google)
A -- Subdomain --> E 
E ----> F(mail) 
E ---> G(drive)
E ----> H(maps)
```

## Some DNS Commands

    cat >> /etc/resolv.conf
    cat >> /etc/hosts
    nslookup www.google.com
    dig www.google.com


#  Application Basics

## Types of Programming Language

**Complied Language**: They are first developed, complied and executed. eg. Java, C, C++
**Interpreted Language**: They first developed and executed. eg. Python, NodeJS, Ruby

## Complied Language

**Develop Source Code**

    public class MyClass {
	    public static void main(String[] args) {
		    System.out.println("Hello World");
        }
    }

**Complie**

    javac MyClass.java

**Run**

    java MyClass

## Interpreted Language

**Develop Source Code**
**Run**

## Java
This is a free, open source programming language. 
Java Development Kit (JDK): This is a set of tool that will help develop, build and run java applications on a system.

**Develop**
Jdb - Debug
Javadoc - Document                
**Build**
Jarc - Compile
Jar - Archive code into a single jar file
**Run**
JRE - Java runtime environment
Javacli - command line

### Build Java Tools
Build tools help automate the build steps such as; complie. doc, creating deployment jar file.
**Maven**
**Gradle**
**ANT**
### some java commands

    Java --version
    javadoc –d doc MyClass.java
    javac MyClass.java
    jar cf MyClass.jar ..
    javadoc MyClass.java

## NodeJS

It took javascript out of the web browsers into the serverside. This is a serer into the serverside javaside environment that can be used to develop applications such as webservers using Javascript.

- NodeJs can handle a large number if connections which makes it a cross platform compartible

**NPM**: Allows developers to develop new reusable pacakges or modules and share then on the public.

### some commands for NodeJS

    yum install nodejs
    node -v
    node add.js
    npm -v
    npm search file
    npm install file
    node -e "console.log(module.paths)"
    npm install file -g

**Built-In Modules**: This are the modules installed automatically at runtime.
- fs - To handle filesystem
- http - To host an HTTP server
- os - To work with the Operating System
- events - To handle events
- tls - To implement TLS and SSL
- url - To Parse URL Strings

**External Modules**
- express - Fast, unopinionated, minimalist web
- framework
- react - To create user interfaces
- debug - To debug applications
- async - To work with asynchronous JS
- lodash - To work with arrays, objects, strings etc

### Built-In Modules

    ls /usr/lib/node_modules/npm/node_modules/
### External Modules

    ls /usr/lib/node_modules/

## Python
 ### some python commands
 

    yum install python2
     yum install python36
     python3 -V
     python2 main.py
     pip3 -V
     pip install flask
     pip show flask
     python2 -c "import sys; print(sys.path)"
     pip install flask --upgrade
     pip install –r requirements.txt
     easy_install install app
     pip install app.whl
