<div id="header" align="center">
  <img src="https://media.giphy.com/media/aXE4aGVPDs1pGcm0y4/giphy.gif" height="338" width="600"/>
</div>

<h1 align="center">Sui</h1>

## Install segala keperluan
```
sudo apt update \
&& apt-get install -y --no-install-recommends \
apt-transport-https \
ca-certificates \
curl \
software-properties-common
```

## Install Docker & Docker Compose ( Jika belum )
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt update \
sudo apt install docker-ce
```

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Buat Directory untuk Sui

```
mkdir -p $HOME/Sui
cd $HOME/Sui
```

#### Download file **YAML**
```
wget -O $HOME/Sui/fullnode-template.yaml https://github.com/MystenLabs/sui/raw/main/crates/sui-config/data/fullnode-template.yaml
```

#### Download dockerfile
```
IMAGE="mysten/sui-node:2d07756360c28e35d7c60816bb0f1ed94ccf356e"
wget -O $HOME/Sui/docker-compose.yaml https://raw.githubusercontent.com/MystenLabs/sui/main/docker/fullnode/docker-compose.yaml
sed -i.bak "s|image:.*|image: $IMAGE|" $HOME/Sui/docker-compose.yaml
```

#### Download genesis.blob
```
curl -fLJO https://github.com/MystenLabs/sui-genesis/raw/main/testnet/genesis.blob
```

#### Run
```
docker compose up -d
```

### Cek logs
```
docker compose logs -f
```
