###### tags: `roadrunner` `ws+broadcast`

# Compile RR `v2.12.0` with the deprecated websockets and broadcast plugins.

### <center>Velox config</center> 

To compile RR binary with the deprecated `websockets` and `broadcast` plugins you have two options:

1. Clone the RR and add these plugins to the list of plugins [here](https://github.com/roadrunner-server/roadrunner/blob/master/container/plugins.go), then compile the RR binary with the following command (assuming that you're inside the cloned repository): `CGO_ENABLED=0 go build -trimpath -ldflags "-s" -o rr cmd/rr/main.go`.

2. Use [Velox](https://github.com/roadrunner-server/velox) and add these plugins to the `velox.toml`. Here is the Dockerfile sample: [link](https://github.com/roadrunner-server/velox/blob/master/Dockerfile_custom_rr)

```toml
# ...
    websockets = {ref = "v3.1.0", owner = "roadrunner-server", repository = "websockets"}
    broadcast = {ref = "v3.1.0", owner = "roadrunner-server", repository = "broadcast"}
# ...
```