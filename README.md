# Welcome to EWOK!

EWOK is the Electronic Warfare Operations Kit, a lightweight RF simulator designed to provide hands-on signal characterization and jamming without the need for expensive equipment.  EWOK offers the ability to create multiple scenarios and environments for students to engage in and enables instructors the flexibility to create scenerios as they please!

## Required Hardware

EWOK is designed with multiple users in mind.  While there are use cases for deploying EWOK on a single non-networked machcine, this is not the intended use case.  EWOK is intended to be deployed on an instructor's computer (the server) and students (the clients) connect to that server via a locally-hosted network.  The server's computer does not need to be powerful or fast to host EWOK.  However, it does need administrator privliges to install the necessary software.  The client machines do not need administrator privleges because they will not need to install any software.  They will access EWOK through the website hosted by the server.  

The typical network setup is a general consumer-grade wireless router.  This router will not need internet access once deployed, but the instructor's server computer will need to access the internet for the installation process.  There are many ways to configure the network that have their own pros/cons, but they are outside the scope of this guide.  This setup guide will only detail how to setup a typical EWOK installation.  

## Required Software
EWOK can be installed on any operating system, although the installation instructions are slightly different.  For the most simple install, a Mac (or Linux) operating system is preferred but any OS will work.

### Required/Recommended Software for Windows:
* [Git](https://git-scm.com/download/win)
* [Node.js and Node Package Manager (NPM)](https://nodejs.org/en/download/package-manager)
    * Install whatever the most current Long-Term Support (LTS) software version is.
    * Node's website instructs you to install Node.js using Fast Node Manager (FNM), Chocolatey, or Docker.  I recommend using [FNM](https://github.com/Schniz/fnm) but FNM has it's own required software.
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)
    * Docker's installer differentiates between AMD and ARM Chipsets.  You're *probably* going to select 'Download for Windows - AMD64' but to check you can pressing the Windows key + R and running 'msinfo32'.  Look for 'Processor.'  If it doesn't say "ARM" then it's probably not 😁
* Google Chrome
    * While EWOK supports most browsers, it was developed using Chrome and so you'll run into fewer issues if you use Chrome as well.
* Visual Studio Code (or your preferred code editor)
    * This isn't *necessary* but there will be a few things you need to adjust in the code.  Use whatever you prefer.

Note:  Some parts of the install process can be made much easier by using Windows Subsystem for Linux (WSL).  Other parts become more difficult.  If you find yourself needing to troubleshoot outside the scope of this guide, I recommend using WSL.  It's a little less user-friendly, but most of the commands you'll find on the internet will just work if you're using WSL.  This guide assumes you're not using WSL, but I wanted to mention it.

### Requirements and Recommendations for Mac/Linux

## Installation
1. On [Github](https://github.com/bjhufstetler/ewok), click "Code" and select "HTTPS", then copy the URL to your clipboard.  

<img align="right" width="300" src="https://firstcontributions.github.io/assets/Readme/clone.png" alt="clone this repository" /> 


<img align="right" width="300" src="https://firstcontributions.github.io/assets/Readme/copy-to-clipboard.png" alt="copy URL to clipboard" />

2. Open PowerShell and navigate to your Desktop (or preferred installation location.  This guide will reference the Desktop).  You can use the `dir` command to see the files in whaterver directory you're in and `cd directory` to navigate to other folders where 'directory' is the directory's name.  Example:  `cd Desktop` to go to the Desktop folder.  You can also run `cd ..` to navigate one directory backwards.

    Note:  OneDrive might complicate this step.  There is a folder called "Desktop" located at C:\Users\YourUsername\Desktop but OneDrive also has a "Desktop" folder located at C:\Users\YourUsername\OneDrive\Desktop.  Check both if your files are suddenly missing!

3. Run `git clone https://github.com/bjhufstetler/ewok`.  Install Git if you haven't already before completing this step.   

### Here will be some steps about configuring the default password and IP address.  Also need to add steps about setting up the router buuuuut not right now.

4. Once completed, navigate into the 'ewok' folder that was created by typing `cd ewok`.  Run the command `npm i` in the ewok folder.  Navigate to the api folder (`cd api`) and run `npm i` again.  Navigate backwards (`cd ..`) and then to the ui folder (`cd ui`) and run `npm i` one final time.  Then navigate back to the main ewok folder with `cd ..`

    Note:  NPM will show a bunch of warnings about depricated software and critical vulnerabilities.  These can be ignored and are normal.

5. Run `docker compose build` and wait.  This will take a little bit.

6. Run `docker compose up` to bring up EWOK.  This can take five minutes or longer, so don't worry if it seems like nothing is happening.  


Git
<br>
npm
<br>
Docker
## To run: 
../ > git clone git@github.com:bjhufstetler/ewok.git
<br>
../ewok/api > npm i
<br>
../ewok/ui > npm i
<br>
../ewok > docker compose up
