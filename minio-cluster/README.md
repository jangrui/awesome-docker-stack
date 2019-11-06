# Minio Cluster swarm setup

A simple setup to deploy Minio using `docker stack deploy` (Swarm).

## Requirements

1. Install [Docker](http://docker.io).
2. Clone this repository
3. Add Labels
3. Create secret
4. Deploy

## Usage

Deploy this stack on a manager node inside your Swarm cluster:

```
# Add Labels
docker node update --label-add minio1=true <node_name1>
docker node update --label-add minio2=true <node_name2>
docker node update --label-add minio3=true <node_name3>
docker node update --label-add minio4=true <node_name4>

# Create secret 
echo "AKIAIOSFODNN7EXAMPLE" | docker secret create access_key -
echo "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY" | docker secret create secret_key -

# Deploy
docker stack deploy --compose-file=docker-stack.yml minio
```

You can then access Minio by using the IP address of any node in your Swarm cluster over port 900[1:4] with a web browser.
