# whiskey-wikimap
## A TiddlyMap kata

The excellent folks at Pop Chart Lab have created a network visualization of [THE MANY VARIETIES OF WHISKEY](https://www.popchartlab.com/products/the-many-varieties-of-whiskey).

This repo is the result of a collaborative exercise to model this network at DevMynd on April 6, 2018 as an exercise in learning about TiddlyMap, networks, and wikis.


## Getting Started

```
# Start a maptime container
make run

# After the container starts, open the wiki in your default browser.
make open
```

Any changes you make will be saved automatically in the `wiki` directory.

At this point you're ready to push to a shared server. You can use your wiki as a personal knowledge base, or easily share it with others who can clone your repo. Assuming they also have Docker, they're a `make run open` away from becoming editors.

## Docker Quickstart

If you're new to Docker, you'll need to get a Docker host running.

### OS X

Tested on macOS High Sierra, 10.13.3:

    brew install docker-compose
    brew install xhyve
    brew install docker-machine-driver-xhyve

    # Enable superuser privileges to access the hypervisor
    sudo chown root:wheel /usr/local/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
    sudo chmod u+s /usr/local/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve

    # Restart the nfs daemon
    sudo nfsd restart

    # Create a new docker machine instance
    docker-machine -D create --driver xhyve --xhyve-experimental-nfs-share dev

    # Set environment variables to communicate with Docker
    eval $(docker-machine env dev)

    # Ensure you can connect
    docker ps
