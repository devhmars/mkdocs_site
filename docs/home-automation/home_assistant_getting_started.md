# **Home Assistant Getting Started**

### What is Home Assistant

Home Assistant is an open-source software that allows you to automate and ingrate with over a thousand different devices and services. Think of it as Alexa Routines but on **Mega** steroids. Home Assistant is ran locally within your home meaning your data is kept locally.

### Getting Started

There are many ways to install Home Assistant which can be found on their [site](https://www.home-assistant.io/). But in this guide I will explain how to install Home Assistant on a linux ubuntu machine using Docker and Docker Compose.

### Prerequisites

  1. You must have a linux machine which you can SSH into guides on how to create a linux server/machine can be found [here]().
  2. You must then SSH on to the machine and install docker and docker-compose guides for this are [here]().
  3. Now we need do install portainer to manage and view our docker containers to do this we can create a `docker-compose.yml` in the `/opt` directory.
  4. Once you are in the `/opt` directory create a file using the following command.

    
        sudo nano docker-compose.yml
    

 5. Copy the following code into the terminal.
   
        version: '3'

        services:
         portainer:
           image: portainer/portainer-ce:latest
           container_name: portainer
           restart: unless-stopped
           volumes:
             - /etc/localtime:/etc/localtime:ro
             - /var/run/docker.sock:/var/run/docker.sock:ro
             - ./portainer-data:/data
           ports:
             - 9000:9000

 6. Once you have done `Ctrl + X` & `Shift + Y` to Save the file and back in the `/opt` directory run.
   
        docker-compose up -d

 7. If you have 0 errors in your terminal then navigate to `https://localhost:9000/` and Portainer should ask you to sign in. **Congrats you just got Portainer up and running!**
    
