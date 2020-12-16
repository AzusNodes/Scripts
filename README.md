# AZUS
Shell script to install a [AZUS Masternode](https://azusnodes.com/) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget https://raw.githubusercontent.com/AzusNodes/Scripts/main/install-MN-16.0.4.sh
bash install-MN-16.0.4.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the AZUS Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send Current Collateral amount of AZU to **MN1**. You need to send all coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **SETTINGS -> Debug -> Console**  
6. Type the following command: **getmasternodeoutputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
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
10. Select your MN and click **Start Inactive/s** to start it.
11. Alternatively, Go to  **SETTINGS -> Debug -> Console** and type:
```
startmasternode alias false "MN1"
```
12. Login to your VPS and check your masternode status by running the following command:.
```
azus-cli getmasternodestatus
```
***

## Usage:
```
azus-cli mnsync status
azus-cli getmasternodestatus  
azus-cli getinfo
```

***
