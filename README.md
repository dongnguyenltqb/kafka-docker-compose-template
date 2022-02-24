## Prepare
- client tunnel is an container which setup an ssh tunnel to server and forward traffic from server to current container network.
- we mount private key to tunnel container and use openssh-client to setup connection
- edit ENTRYPOINT in client-tunnel/Dockerfile 
-
## Build
```
docker-compose up -d --build
```

## Post build
after up run the command below
```
sudo chown -R 1000 kafka1_data kafka2_data kafka3_data zoo_log zoo_data
```
