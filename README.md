# Joinmarket Docker Container

## What?

This automates the process for Joinmarket in a nice docker Container

## Why?

* Ease of use
* Everyone should put their full node to use
* Everyone should mix
* Everyone should be able to be a market maker (fuck DEFI, bitcoin is the real DEFI)

## Usage Notes

### Wallettool command


```bash
# Param can be 'generate' '--help' or the wallet filename (eg. wallet.jmdat)

PARAM='wallet.jmdat'

docker run --rm  -it --network host \
        -v $HOME/.joinmarket:/data/.joinmarket \
        -v $HOME/.bitcoin:/data/.bitcoin \
        --entrypoint="/joinmarket-clientserver/scripts/wallet-tool.py" \
        --name joinmarket \
        lncm/joinmarket:v0.7.0 $PARAM
```

## Build Notes

### Maintainer Notes

### Github Action Environment Variables

* `DOCKER_USERNAME` - (required) Username to access docker hub
* `DOCKER_PASSWORD` - (required) Password associated with the username. Can be a token too.
* `DOCKER_HUB_USER` - (required) docker hub username if `DOCKER_USERNAME` differs, in this case  an organization. It can be the same too but its required
* `MAINTAINER_USER` - (optional) Username for github to use Github Container Registry
* `MAINTAINER_TOKEN` - (optional) Personal Access token for github which accesses Github Container Registry.

### Building Notes

```
docker build -t lncm/joinmarket .
```

### Inspecting the Container

```
docker run --rm --entrypoint="/bin/bash" -it lncm/joinmarket:v0.7.0
```
