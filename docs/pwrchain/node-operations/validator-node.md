---
title: Validator Node
sidebar_position: 1
---

# How to Run a Validator Node

**Requirements:**

- **CPU**: 1 vCPU
- **Memory**: 1 GB RAM
- **Disk**: 25 GB HDD or higher
- **Open TCP Ports**: 8231, 8085
- **Open UDP Port**: 7621

### Setup on Ubuntu Server:

1. **Update OS**:

```shell
sudo apt update
```

2. **Install Java**:

```shell
apt install openjdk-19-jre-headless
```

3. **Install the validator node software and config file**:

```shell
wget https://github.com/pwrlabs/PWR-Validator-Node/raw/main/validator.jar
wget https://github.com/pwrlabs/PWR-Validator-Node/raw/main/config.json
```

4. **Set Up your Password**:

```shell
sudo nano password
```

- Enter your desired password.
- Press `Ctrl + x` to close.
- Press `Y` to confirm saving the password.

5. **Run the Node: Replace `<YOUR_SERVER_IP>` with your server's actual IP**:

```shell
sudo java -jar validator.jar password <YOUR_SERVER_IP> --compression-level 0
```

PWR Chain is the first chain that supports block compression. --compression-level sets the level of compression you want your node to use. Compression level varies from 0 - 9. 0 disbales compression. 9 sets it to maximum.

- Upon initialization, the node will generate a wallet, store it locally, and display an address in the format:
  
  ```js
  My address: 0xf4b2f12afa634c206bdf5f0dd6dd90f024ad62b7
  ```

6. **Become a Validator Node**:

- Initially, your node will synchronize with the blockchain but will not assume validator responsibilities until it possesses staked PWR Coins.
- To obtain sufficient PWR Coins for staking, [apply to become a testnet validator on our Discord server](https://discord.gg/DJkcuy9SAg). Once approved, you can use our discord bot to claim 100k PWR to stake.
- After claiming your coins, your node will initiate a transaction to enlist as a validator.

7. Running in the Background: If you wish to run the node in the background, ensuring it remains active after closing the terminal, utilize the `nohup` command:

```shell
nohup sudo java -jar validator.jar password <YOUR_SERVER_IP> --compression-level 0 &
```

Congratulations, you've now set up and run a PWR Chain validator node!
