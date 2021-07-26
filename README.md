olive-tin-headstart
# OliveTin - Headstart

Based on "OliveTin — a simple web interface for running Linux shell commands" at https://medium.com/james-reads-public-cloud-technology-blog/olivetin-a-simple-web-interface-for-running-linux-shell-commands-41d57f645ebc

GitHub Project Source Code: https://github.com/OliveTin/OliveTin

Documentation: https://docs.olivetin.app/

Home Page: https://olivetin.app/

## 100 - Installation

See [README.md](./100/README.md)

## 200 - Configuration

OliveTin is controlled by a ```config.yaml``` file. On startup, it looks for this file in the following locations;

1. The current working directory (./)

2. /config/ - Mostly used for containers

3. /etc/OliveTin/ - this is the recommended directory on Linux for your config.yaml.

The most simple ```config.yaml``` would be something like this;

```
actions:
  - title: "Hello world!"
    shell: echo 'Hello World!'
``` 
containers/olivetin/config.yaml

In the "Actions" section of this documentation you can find lots of examples of how to setup additional actions.
