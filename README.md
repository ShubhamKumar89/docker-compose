# docker compose installation

Method 1 and method 2 require `Docker Engine` and `Docker CLI` as prerequisites for `docker compose` installation.

## Method 1 - Install using the repository

1. For Ubuntu and Debian, run:

```bash
sudo apt-get update
sudo apt-get install docker-compose-plugin
```

2. To Verify

```bash
docker compose version
```

## Method 2 - Install the plugin manually

1. To download and install the Compose CLI plugin, run:

```bash
DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
mkdir -p $DOCKER_CONFIG/cli-plugins
curl -SL https://github.com/docker/compose/releases/download/v2.18.1/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
```

This command downloads the latest release of Docker Compose (*from the Compose releases repository*) and installs Compose for the active user under `$HOME` directory.

> **Note**: **To install:** <br>
>> - Docker Compose for all users on your system, replace `~/.docker/cli-plugins` with `/usr/local/lib/docker/cli-plugins`. <br>
>> - A different version of Compose, substitute `v2.18.1` with the version of Compose you want to use. <br>
>> - For a different architecture, substitute `x86_64` with the [architecture you want](https://github.com/docker/compose/releases). <br>

2. Apply executable permissions to the binary:

```bash
chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose
```

3. Test the installation.

```bash
docker compose version
```

## Method 3 - Install Compose standalone

1. To download and install Compose standalone, run:

```bash
curl -SL https://github.com/docker/compose/releases/download/v2.18.1/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
```

2. Apply executable permissions to the standalone binary in the target path for the installation.

```bash
sudo chmod +x /usr/local/bin/docker-compose
```

3. Test and execute compose commands using `docker-compose`.

> **Note**:
> Compose standalone uses the `-compose` syntax instead of the current standard syntax `compose`.
> For example type `docker-compose up` when using Compose standalone, instead of `docker compose up`.
