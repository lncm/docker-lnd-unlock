# LND Unlock Container

![Docker Pulls Count](https://img.shields.io/docker/pulls/lncm/lnd-unlock.svg?style=flat)


This is a helper container for unlocking LND for unattended installs. 

For best results use this within docker-compose


## Clone directory

```bash
docker pull lncm/lnd-unlock
```

## Pathnames Required

- /lnd/data/chain/bitcoin/$NETWORK/admin.macaroon (Where: $NETWORK is the network. This is the LND default path. Best to leave this alone)
- /secrets/lnd-password.txt (This is the unlock password. Must be readable by this container)

## Environment Variables

- LNDHOSTNAME (default: lnd) : This is the hostname for the lnd instance. Can be an IP
- HOSTIPPORT (default: 10.254.2.3:8080) : This is the IP and port for the LND rest interface.
- NETWORK (default: mainnet) : This is the network that LND uses and how to find the correct macaroon file

## Quick run

```bash
docker run -d --rm \
            lncm/lnd-unlock:1.0.2 \
            --name=lnd-unlock \
            -v $HOME/lnd:/lnd \
            -v $HOME/secrets:/secrets \
            -e HOSTIPPORT=10.254.2.3:8080 \
            -e NETWORK=mainnet \
            -e LNDHOSTNAME=10.254.2.3
```

