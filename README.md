# LND Unlock Container

![Docker Pulls Count](https://img.shields.io/docker/pulls/lncm/lnd-unlock.svg?style=flat)


This is a helper container for unlocking LND for unattended installs. 

For best results use this within docker-compose

## Environment Variables

- LNDHOSTNAME (default: lnd) : This is the hostname for the lnd instance. Can be an IP
- HOSTIPPORT (default: 10.254.2.3:8080) : This is the IP and port for the LND rest interface.
- NETWORK (default: mainnet) : This is the network that LND uses and how to find the correct macaroon file
