This Project aims to provide an "straight-forward" way to create a swarm-cluster with Portworx (px-dev) as Volume-Driver for the Swarm.
Portworx enables Cluster aware Volumes in an hyper-converged way.

Advice: For DEV Env!

#### Req:
- 3 VMs (unformated disk on each VM) - Recommand: Scaleway VC1M
- Docker V1.13


#### Create the Swarm
```
docker swarm init
docker swarm join-token manager
```
Execute the Output on the 2 other node to join the Cluster (3 Manager Nodes)


#### Setup
```
git clone https://github.com/Berndinox/swarm_webstack && cd swarm_webstack
docker stack deploy --compose-file consul.yaml consul
cp config.json /etc/pwx/
sh start_px.sh
```
