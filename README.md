# Ardupilot SITL, Containerized

Run [ardupilot's software-in-the-loop
(SITL)](https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html)
locally in a Docker container.

```sh
docker buildx build -t uaarg-sitl -f SITL.Dockerfile .  # Build the container (takes ~20mins on my machine)
docker run -p 5760:5760 --rm -it uaarg-sitl:latest      # Run the container

# Connect to the SITL instance, eg. with mavproxy
mavproxy.py --master=tcp:127.0.0.1:5760
```

## TODO

We should build the uaarg-sitl container in GitHub's CI so getting started can
take less time.
