### Docker Image
Drone Server
```
docker save -o drone-2.11.1-linux-amd64.tar drone/drone:2.11.1-linux-amd64
```
[docker pull drone/drone:2.11.1-linux-amd64](./drone-2.11.1-linux-amd64.tar.xz)

Drone Runner (Docker Runner)
```
docker save -o drone-runner-docker-1.8.1-linux-amd64.tar drone/drone-runner-docker:1.8.1-linux-amd64
```
[docker pull drone/drone-runner-docker:1.8.1-linux-amd64](./drone-runner-docker-1.8.1-linux-amd64.tar.xz)

### Gitea Integration
Drone integrates seamlessly with popular Source Control Management providers.

[Gitea](https://docs.drone.io/server/provider/gitea/)

### Start Drone Server (Docker)
```bash
docker run \
  --volume=/var/lib/drone:/data \
  --env=DRONE_GITEA_SERVER=https://try.gitea.io \
  --env=DRONE_GITEA_CLIENT_ID=05136e57d80189bef462 \
  --env=DRONE_GITEA_CLIENT_SECRET=7c229228a77d2cbddaa61ddc78d45e \
  --env=DRONE_RPC_SECRET=super-duper-secret \
  --env=DRONE_SERVER_HOST=drone.company.com \
  --env=DRONE_SERVER_PROTO=https \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  --detach=true \
  --name=drone \
  drone/drone:2.11.1-linux-amd64
```

### Start Drone Runner (Docker Runner)
```bash
docker run --detach \
  --volume=/var/run/docker.sock:/var/run/docker.sock \
  --env=DRONE_RPC_PROTO=https \
  --env=DRONE_RPC_HOST=drone.company.com \
  --env=DRONE_RPC_SECRET=super-duper-secret \
  --env=DRONE_RUNNER_CAPACITY=2 \
  --env=DRONE_RUNNER_NAME=my-first-runner \
  --publish=3000:3000 \
  --restart=always \
  --name=runner \
  drone/drone-runner-docker:1.8.1-linux-amd64
```

### Start Drone Runner (Exec Runner)(Beta)
[Install the Exec Runner for Windows](https://github.com/drone-runners/drone-runner-exec/releases/latest/download/drone_runner_exec_windows_amd64.tar.gz)