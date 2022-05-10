# Deploy services to swarm cluster with stack
## Step 0 : make cluster with swarm
Run bellow comands in terminal to make a manager node:
```
$ docker swarm init
```
Output:
```
Swarm initialized: current node (gxevzf2y3yy8kjpbfy4joyvff) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-3zv10u2c02zdlg4smu8zv3m56bjcvsrwtlwf47xbi00s7s0uun-3o8a98ag8ef08niiot9irqt5c 192.168.99.1:4242

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

```
All computers in local network can join to this swarm manager with bellow command:
```
$ docker swarm join --token SWMTKN-1-3zv10u2c02zdlg4smu8zv3m56bjcvsrwtlwf47xbi00s7s0uun-3o8a98ag8ef08niiot9irqt5c 192.168.99.1:4242
```
## Step 1 : deploy services to cluster with stack
Download my-stack.yml file and run bellow command in manager node:
```
$ docker stack deploy --compose-file my-stack.yml my-services
```
Output:
```
Creating network my-services_e2e
Creating service my-services_central
Creating service my-services_analyze
Creating service my-services_visualizer
```
