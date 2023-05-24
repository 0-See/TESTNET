<p align="center">
<img width="100" height="100" src=https://github.com/0-See/TESTNET/assets/128711050/c92c296c-b863-4704-a724-cf7a9bddb904
</p>

# Testnet v2 Validator Setup Guide

### [Tracking your validator's metrics](https://metrics.elixir.finance/)

### Preparation – System Setup

### Installing docker

```bash
curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh
```

### Create a directory

```bash
mkdir elixir
cd elixir
```

### Download the Dockerfile

```bash
curl -O https://files.elixir.finance/Dockerfile
```

### Edit Dockerfile

### Enter the metamask wallet address in ENV ADDRESS and the private key in ENV PRIVATE_KEY

```bash
nano Dockerfile
```

### Build the Docker image

```bash
docker build . -f Dockerfile -t elixir-validator
```

### Start your validator

```bash
docker run -d --restart unless-stopped --name ev elixir-validator
```

### Getting the latest version

```bash
cd elixir
docker kill ev
docker rm ev
docker pull elixirprotocol/validator:testnet-1
docker build . -f Dockerfile -t elixir-validator
```

### And rerun the docker command to start the validator:

```bash
docker run -d --restart unless-stopped --name ev elixir-validator
```
