# Sui-Blockchain-Programmer-Guide

# Installation Instructions

This is a brief outline of the installation and setup instructions of the SUI Blockchain.


## Step 1: Install SUI

## Windows
#### Check for Chocolatey
execute the following command on the command prompt to see if you have chocolatey installed on your laptop:
```shell
choco --version
```
if you have it installed proceed to Install SUI with Chocolatey.
If you don't have Chocolatey installed, follow the steps below to install/enable Chocolatey:
### Install chocolatey
#### 1. Execute one of the following commands to set execution policy:
```shell
Set-ExecutionPolicy AllSigned
```
OR
```shell
Set-ExecutionPolicy Bypass -Scope Process
```
#### 2. Download and executes the installation script for Chocolatey:
```shell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
### Install SUI using Chocolatey
#### Run the command prompt with admin privileges.
The best way to install SUI on windows is by using Chocolatey, so execute the following command:
```shell
choco install sui
```
## Mac
Using homebrew
```shell
brew install sui
```
### Verify the installation:
```shell
sui --version
```
## Step 2: Configure SUI Client
#### 1. To connect the Sui client to a network, run the following command:
```shell
sui client
```
If you receive the sui-client help output in the console, you already have a client.yaml file.;nspb
The first time you start Sui client without having a client.yaml file, the console will display the following message:
```shell
Config file ["<PATH-TO-FILE>/client.yaml"] doesn't exist, do you want to connect to a Sui Full node server [y/N]?
```
Press y and then press Enter. The process then requests the RPC server URL:

```shell
Sui Full node server URL (Defaults to Sui Testnet if not specified) :
```
Press Enter to connect to Sui Testnet.
The console should then display a prompt to generate a new address:
```shell
Select key scheme to generate keypair (0 for ed25519, 1 for secp256k1, 2 for secp256r1):
```
Press 0 and then press Enter.

This will output the address and a mnemonic phrase which you should backup and keep safe. This is essentially your private key. Sui returns a message similar to the following.

```shell
Generated new keypair for address with scheme "ed25519" [0xb9c83a8b40d3263c9ba40d551514fbac1f8c12e98a4005a0dac072d3549c2442]
Secret Recovery Phrase : [cap wheat many line human lazy few solid bored proud speed grocery raise erode there idea inform culture cousin shed sniff author spare carpet]
```
You can check your active address via:
```shell
sui client active-address
```
## Step 3: Request SUI Tokens through cURL
Use the following cURL command to request tokens directly from the faucet server:
```shell
curl --location --request POST 'https://faucet.devnet.sui.io/gas' \
--header 'Content-Type: application/json' \
--data-raw '{
    "FixedAmountRequest": {
        "recipient": "<YOUR SUI ADDRESS>"
    }
}'
```
Paste your active address where it says <YOUR SUI ADDRESS>
#### You can check your balance via:
```shell
sui client gas
```
You should see an output that looks like this:
```shell
                             Object ID                              |  Gas Value
----------------------------------------------------------------------------------
 0x942828410188f554c6436ee26eb50b2155864969135a91cc07f93f1f9255f1e8 | 10000000000
```
Happy Coding!!👨🏽‍💻






