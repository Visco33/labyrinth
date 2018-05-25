# Labyrinth Coin
Shell script to install a [Labyrinth Masternode](https://labyrinthcoin.space) on a Linux server running Ubuntu 16.04. Use it on your own risk.

***
## Installation:
Command 1:
```
wget -q https://raw.githubusercontent.com/Visco33/labyrinth/master/labyrinth.sh
```
Command 2: 
```
bash labyrinth.sh 
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Labyrinth Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **5000** **LBN** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.

***

## Usage:

```
labyrinthd mnsync status
labyrinthd getinfo
labyrinthd masternode status
```

Also, if you want to check/start/stop **labyrinth** , run one of the following commands as **root**:

```
systemctl status labyrinth #To check the service is running.
systemctl start labyrinth #To start labyrinth service.
systemctl stop labyrinth #To stop labyrinth service.
systemctl is-enabled labyrinth #To check whether or not the labyrinth service is enabled on boot or not.
```

***
Credit to Zoldur for his amazing shell base.
