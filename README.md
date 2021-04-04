# Ethical Hacking

Why I start this project is not for hacking or ethical hacking, which was my dream of childhood, basically I just would like to dive into network meanwhile to do something interesting. Learning by doing is always the best way in the computer world.

## What's the expection during this project?
- Understand the devices, protocols, mechanism, algorithms of network
- Master Python
- Be familiar with toolkit for Network Troubleshooting

## Preparation
First of all, we need to setup the experiment enviroument, because most OS of servers that running in the real world are Linux, besides lots of commands are different between Linux and Mac, so running Kali Linux on Mac is coming into the picture, while VM is quite heavy and the graph UI is not necessary actually, finally the env is as follows:
- Mac Laptop
- Docker on Mac
- Kali Linux Docker Image

### Build Docker Image
- Pull the original docker image from docker hub
  - `docker pull kalilinux/kali-rolling` (refer to [Official Kali Linux Docker Images](https://www.kali.org/docs/containers/official-kalilinux-docker-images/))
- Run the image as a container and login  
  - `docker run --name kali -it kalilinux/kali-rolling`
- The basic container only supports a few commands, install some necessary commands manually
	- `apt udpate` (udpate the package list, usually at `/etc/apt/source.list`)
	- `apt upgrade` (upgrade following the list)
	- `apt install kali-linux-top10`
	- `apt install python3-pip`
	- `apt install vim`
	- `apt install iputils-ping`
	- `apt install iproute2`
	- Btw to make it easy, can just pull my image which will be keep being updated (`docker pull chejinying/kali`
- Commit the changes
  - check the container id: `docker ps`
  - `docker commit -m "install basic network command" e17d1cfd07b0 chejinying/kali`
- Push the image to Docker Hub
  - `docker image push chejinying/kali`
