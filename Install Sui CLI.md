### Install Rust
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### Install Keperluan
```
sudo apt update && sudo apt install -y curl git libssl-dev libclang-dev tzdata ca-certificates build-essential pkg-config cmake screen
```

### Install Sui
```
cargo install --locked --git https://github.com/MystenLabs/sui.git --branch testnet sui
```
Tunggu, lumayan lama

### Connect ke chain
```
cargo install --git https://github.com/move-language/move move-analyzer --features "address20"
```
### Generate Wallet
```
sui client active-address
```
y, lalu Enter
<p align="left"><img height="auto" width="auto" src="https://user-images.githubusercontent.com/98658943/214794966-066509ce-17b1-4f01-8ebf-22fde0671afb.png"</p>

Enter
<p align="left"><img height="auto" width="auto" src="https://user-images.githubusercontent.com/98658943/214795329-d9026e34-3f98-4cfe-94fa-fe3334298c92.png"</p>

 0 , lalu Enter
<p align="left"><img height="auto" width="auto" src="https://user-images.githubusercontent.com/98658943/214795390-eb847ffe-2fc6-4a6d-a435-bbf04d9ebd3c.png"</p>

**BACKUP** Mnemonic dan Address

### Masuk ke discord Sui
https://discord.gg/sui

- Req Faucet
```
!faucet AddressMu
```



#### Jika `command not found`
```
rustup update stable
source "$HOME/.cargo/env"
```

### Jalankan Node
```
git clone https://github.com/MystenLabs/sui.git --branch testnet
cd sui
git remote add upstream https://github.com/MystenLabs/sui
```

### Fetch
```
git fetch upstream
```

### Membuat file fullnode.yaml
```
cp crates/sui-config/data/fullnode-template.yaml fullnode.yaml
```

### Download genesis.blob
```
curl -fLJO https://github.com/MystenLabs/sui-genesis/raw/main/devnet/genesis.blob
```

### RUN
```
screen -S sui
cargo run --release --bin sui-node -- --config-path fullnode.yaml
```

Tunggu sampai selesai, setelah selesai CTRL+A+D untuk keluar

