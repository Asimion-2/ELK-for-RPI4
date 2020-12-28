# ELK-for-RPI4
Creating a functional ELK stack that reads Egress data via USB on a Raspberry pi 4 

## **Hardware**

### Recommended
- Raspberry pi 4GB

- 5 Volt 3 A power source 

- 8 GB SD card

### Optional
- Raspberry pi 8GB 

- Raspberry pi 4 compatible battery pack

- 64 GB SD card

## **IMPORTANT**
> Please make sure you have a Pi complatiable operation system flashed to your SD card.
>
> Here we are using Ubuntu 20.04 Server edition. [Download here](https://ubuntu.com/download/raspberry-pi)
>
> If havent already done this please download the ISO image and flash it to your SD card via flashing software for example Rufus. [Rufus Download](https://rufus.ie/)
>
> Your Pi must also be connect to your personal network via Wifi or Lan. In this instence we will be using Lan.



## **Setting up**
Personal I created separate directories for each part of my stack.

You can do this via the mkdir command. (Ex: mkdir data, mkdir Elastic, mkdir Kibana, mkdir Logstash)

### Downloading the appropriate software 
You can find all the downloads for each system architecture at [This link](https://www.elastic.co/downloads/)

Since we are on linux I will be using the curl command to download each part of the stack into their respective directorys 
- Elastic Search
  - Curl -O https://tinyurl.com/y9p47ycu
- Kibana 
  - Curl -O https://tinyurl.com/y98v5eyk
- LogStash 
  - Curl -O https://tinyurl.com/yajvt5dd
  
  
  
  
  
  
  








