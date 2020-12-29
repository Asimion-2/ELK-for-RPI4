# ELK-for-RPI4
Creating a functional ELK stack that reads Egress data via USB on a Raspberry pi 4 

## **Hardware**

### Recommended
- Raspberry pi 4GB

- 5 Volt 3 Amp power source 

- 8 GB SD card

### Optional
- Raspberry pi 8GB 

- Raspberry pi 4 compatible battery pack

- 64 GB SD card

## **IMPORTANT**
> Please make sure you have a Pi complatiable operation system flashed to your SD card.
>
> Here we are using Ubuntu 20.04.1 LTS Server edition. [Download here](https://ubuntu.com/download/raspberry-pi)
>
> If havent already done this please download the ISO image and flash it to your SD card via flashing software for example Rufus. [Rufus Download](https://rufus.ie/)
>
> Your Pi must also be connect to your personal network via Wifi or Lan. In this instence we will be using Lan.



## **Preparation**
Personal I created separate directories for each part of my stack.

You can do this via the mkdir command. (Ex: mkdir data, mkdir Elastic, mkdir Kibana, mkdir Logstash)

### Downloading the appropriate software 
You can find all the downloads for each system architecture at [This link](https://www.elastic.co/downloads/)

Since we are on linux I will be using the curl command to download each part of the stack into their respective directorys 

 *Please note that you will have to extract each file after each download with the follow command. Ex: tar -xf elasticsearch*

- Elastic Search
  - curl -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.10.1-linux-aarch64.tar.gz
- Kibana 
  - curl -O https://artifacts.elastic.co/downloads/kibana/kibana-7.10.1-linux-aarch64.tar.gz
- LogStash 
  - curl -O https://artifacts.elastic.co/downloads/logstash/logstash-7.10.1-linux-aarch64.tar.gz
- Tshark (Feel free to use others like Tcpdump but we will be using tshark)
  - sudo apt install tshark
  
## **Configuration**
Congrats! You have successfully aquired everything from stack to data capture. Now its time for the configuration part.


**CD over to the elasticsearch config directory. We will need to edit the jvm.options file and the elasticsearch.yml file** 


I will use the command sudo nano file/name/here but feel free to use whichever text editor you prefer 

- Change the second set of total heap sizes in jvm.options 
  - Xms512m to Xms 1g
  - Xmx512m to Xmx 1g

- Changes in the elasticsearch.yml file
  - Unblock the network.hosts: localhost and http:9200 port line under the Network category 
  - Unblock the discovery.type: single-node under the Discovery catergory 


*Make sure you save everything before contining to the next step of the configuration*


**CD over to the Kibana config directory. Here wwe will edit the kibana.yml file**  
  
  
- Inside the .yml file were gonna need to unblock and change some files
  - Unblock the server.port line and set it to port 5601 if its not already
  - unblock the server.host and make sure you set this to a non-loopbackable address like localhost(Ex: Your PI ip address)
  - Unblock the server.name line and for this example set it to localhost if its not already
  - Unblock elasticsearch.hosts: line so that kibana can actually communicate with elastic


  
*Make sure you save everything before contining to the next step of the configuration*


**CD over to the logstash bin directory. Here we will create a configuration for logstash to run**
  
  
- Inside the bin directory create a file called logstash-json.conf and paste the follwing code [here](https://github.com/Asimion-2/ELK-for-RPI4/blob/main/logstash-json)




