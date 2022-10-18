# Open SOC Setup Guide 

## Installation

Setup Elasticsearch

```bash
  sudo apt update
  sudo apt upgrade
  wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
  sudo apt-get install apt-transport-https
  echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list
  sudo apt-get update && sudo apt-get install elasticsearch
```
The username and password for the elastic user will be displayed right in the terminal itself as soon as the installation is completed. 

Now we need to edit **elasticsearch.yml** 

We need to modify **network.host** parameter and replace our IP address. Save the file and start elasticsearch servies using the commands 

```
systemctl start elasticsearch
systemctl enable elasticsearch
```
You can verify the running status of elasticsearch using the command: 
```
systemctl status elasticsearch
```
