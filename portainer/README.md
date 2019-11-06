# Portainer swarm setup

A simple setup to deploy Portainer using `docker stack deploy` (Swarm).

## Requirements

1. Install [Docker](http://docker.io).
2. Clone this repository
3. Deploy

## Usage

Deploy this stack on a manager node inside your Swarm cluster:

```
docker stack deploy -c docker-stack.yml portainer
```

You can then access Portainer and Visualizer by using the IP address of any node in your Swarm cluster over port 9000 and 8080 with a web browser.
