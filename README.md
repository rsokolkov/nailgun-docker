# Run standalone Nailgun in Docker

This project allows to run standalone [Nailgun](https://github.com/openstack/fuel-web) in Docker.

Nailgun is run in development mode

```
manage.py run --fake-tasks \
              --fake-tasks-tick-count=80 \
              --fake-tasks-tick-interval=1 \
              --authentication-method="none"
```

## Run Nailgun

Build image

```
cd nailgun-docker
docker build -t nailgun:9.1 9.1
```

Run container

```
docker run --name nailgun -d nailgun:9.1
```

Nailgun startup takes some time. Wait for 30 seconds before using container.

## Use Nailgun

Attach with interactive shell

```
docker exec -i -t nailgun /bin/bash
fuel node
```

Run single command

```
docker exec nailgun fuel node
```

## TODO

  * Support older versions

## Known issues

  * No Fuel UI
