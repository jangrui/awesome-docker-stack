# MySQL Galera Cluster swarm setup

A simple setup to deploy MySQL Galera Cluster using `docker stack deploy` (Swarm).

## Requirements

1. Install [Docker](http://docker.io).
2. Clone this repository
3. Deploy

## Usage

Deploy this stack on a manager node inside your Swarm cluster:

```
docker stack deploy -c docker-stack.yml pxc
```

You can then access MySQL Galera Cluster by using the IP address of any node in your Swarm cluster over port 3306 with the TCP.
