# Running an Elixir Validator

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
curl -O https://testnet-1-files.elixir.finance/Dockerfile
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
