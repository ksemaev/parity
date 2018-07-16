# A typical project for starting blockchain nodes

The project consists:
- two [parity containers](https://github.com/paritytech/parity);
- performance monitoring stack with containers prometheus, node-exporter, cadvisor, alert-manager, grafana taken from [here](https://github.com/vegasbrianc/prometheus) with several fixes;
- parity metric exporter from [here](https://github.com/fanatid/parity-exporter);
- log monitoring stack with containers elasticsearch, logstash, kibana, logspout inspired by [this](https://github.com/deviantony/docker-elk) and [this](https://github.com/looplab/logspout-logstash). 

# Pre-requisites
Ensure you install the latest version of docker on your Docker host machine.

# Installation & Configuration
Clone the project locally to your Docker host.

Get into project directory and run

    $ docker-compose up -d
  
As Kibana does not provide provisioning - you'll have to create indexes and filters yourself

# Usage
Grafana will be avalibale at http://your_ip:3000  with admin:foobar

Kibana will be avaliable http://your_ip:5601
 
# ToDo list
- create alerts;
- configure storage and garbage collectors;
- get logs from only application containers.


# Security Considerations
This project is intended to be a quick-start to get up and running. Security has not been implemented in this project. It is the users responsability to implement Firewall/IpTables and SSL.

Since this is a template to get started all services are exposing their ports to allow for easy troubleshooting and understanding of how the stack works.

For production usage consider installing containers at Kubernetes or at least Swarm

