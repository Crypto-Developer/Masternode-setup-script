![Example-Logo](https://i.imgur.com/EectWTn.png)
# Oxygen Masternode Setup Guide (Ubuntu 16.04)
This guide will assist you in setting up a Oxygen Masternode on a Linux Server running Ubuntu 16.04. (Use at your own risk)

If you require further assistance contact the support team @ [Discord](https://discord.gg/)
***
## Requirements
1) **10,000 Oxygen coins**
2) **A VPS (Vultr) running Linux Ubuntu 16.04**
3) **A Windows or MAC OS X local wallet**
4) **An SSH client such as [Bitvise](https://dl.bitvise.com/BvSshClient-Inst.exe)**
***
## Contents
* **Section A**: Creating the VPS within [Vultr](https://www.vultr.com/?ref=7485061)
* **Section B**: Downloading and installing Bitvise
* **Section C**: Connecting to the VPS and installing the MN script via Bitvise
* **Section D**: Preparing the local wallet
* **Section E**: Connecting & Starting the masternode
***

## Section A: Creating the VPS within [Vultr](https://www.vultr.com/?ref=7485061) 
***Step 1***
* Register at [Vultr](https://www.vultr.com/?ref=7485061)
***

***Step 2***
* After you have added funds to your account go [here](https://my.vultr.com/deploy/) to create your Server
***

***Step 3*** 
* Choose a server location (preferably somewhere close to you)

![Example-Location](https://i.imgur.com/JfDqlK0.png)
***

***Step 4***
* Choose a server type: Ubuntu 16.04

![Example-OS](https://i.imgur.com/QUoBqJG.png)
***

***Step 5***
* Choose a server size: $5/mo will be fine 

![Example-OS](https://i.imgur.com/19LGnMe.png)
***

***Step 6*** 
* Set a Server Hostname & Label (name it whatever you want)

![Example-hostname](https://i.imgur.com/UcM4dov.png)
***

***Step 7***
* Click "Deploy now"

![Example-Deploy](https://i.imgur.com/8q0IrLC.png)
***


## Section B: Downloading and installing BitVise

***Step 1***
* Download Bitvise [here](https://dl.bitvise.com/BvSshClient-Inst.exe)
***

***Step 2***
* Select the correct installer depending upon your operating system. Then follow the install instructions

![Example-BitviseInstaller](https://i.imgur.com/V4pZ0ld.png)
***


## Section C: Connecting to the VPS & Installing the MN script via Bitvise

***Step 1***
* Copy your VPS IP (you can find this by going to the server tab within Vultr and clicking on your server

![Example-Vultr](https://i.imgur.com/HwquKWq.png)
***

***Step 2***
* Open the bitvise application and fill in the "Host" box with the IP

![Example-BitviseInstaller](https://i.imgur.com/mVblkp3.png)
***

***Step 3***
* Copy the root password from the VULTR server page
![Example-RootPass](https://i.imgur.com/WHrWxXG.png)
***

***Step 4***
* type "root" as the username
* type "password" as the Initial method
* type password
* then press "Login"

![Example-RootPass](https://i.imgur.com/Ppf3hSD.png)

* then press "Accept and Save"

![Example-RootPass](https://i.imgur.com/7e3cxLY.png)
***

***Step 5***
* Paste the code below into the Bitvise terminal then press enter (it will just go to a new line)

`wget -q https://raw.githubusercontent.com/Oxygencoin/Masternode-Setup-Script/master/oxygencoin_install.sh`

![Example-RootPassEnter](https://i.imgur.com/SQ3wn9b.png)
***

***Step 6***
* Paste the code below into the putty terminal then press enter

`bash oxygencoin_install.sh`

![Example-Bash](https://i.imgur.com/82UVRd0.png)

![Example-installing](https://i.imgur.com/9NiakiG.png)
***

***Step 7***
* When prompted to enter your private key - press enter

![Example-installing](https://i.imgur.com/BcNBa7q.png)
***

***Step 8***
* You will now see all of the relavant information for your server
* Keep this terminal open as we will need the info for the wallet setup

![Example-installing](https://i.imgur.com/RbyldCk.png)
***

## Section D: Preparing the Local wallet

***Step 1***
* Download and install the Oxygen wallet [here](https://github.com/Oxygencoin/oxygen/releases)
***

***Step 2***
* Send EXACLY 10,000 OXG to a receive address within your wallet
***

***Step 3***
* Create a text document to temporarily store information that you will need 
***

***step 4***
* Go to the console within the wallet 

![Example-console](https://i.imgur.com/vGO4E3D.png)
***

***Step 5***
* Type the command below and press enter 

`masternode outputs` 

![Example-outputs](https://i.imgur.com/KfEaj67.png)
***

***Step 6***
* Copy the long key (this is your transaction ID) and the 1, 0 or 2 at the end (this is your output index)
* Paste these into the text document you created earlier as you will need them in the next step
***

# Section E: Connecting & Starting the masternode 

***Step 1***
* Go to the tools tab within the wallet and click open "masternode configuration file"

![Example-create](https://i.imgur.com/Dw50dKu.png)
***

***Step 2***

* Fill in the form
* For `Alias` type something like "mn1" **don't use spaces**
* The `Address` is the IP and port of your server (this will be in the putty terminal that you still have open)
* The `PrivKey` is your masternode private key (This is also in the putty terminal that you have open)
* The `TxHash` is the transaction ID/long key that you copied to the text file
* The `Output Index` is the 0 or 1 that you copied to your text file

![Example-create](https://i.imgur.com/glh2b1I.png)

Click "File Save"
***

***Step 3***
* Close out of the wallet and reopen Wallet
* Wait for the transaction to have at least 15 confirmations
* Go to the console within the wallet
* Type the command below and press enter 

`startmasternode alias 0 mn1` 

![Example-outputs](https://i.imgur.com/NR0v541.png)
***

***step 4***
* Check the status of your masternode within the VPS by using the command below:

`cd /usr/local/bin/`
`./oxygen-cli mnsync status`

* You should see

![Example-status](https://i.imgur.com/GwiacH8.png)

If you do, congratulations! You have now setup a masternode. If you do not, please contact me or any other support 
***

## Donations:  

Any donation is highly appreciated 

**BTC**: 18ByogQfBve4WovYpTC4Hwrv4JAvazhenR  
**ETH**: 0xc749be094ed0f41ac516025e28048f0ad83dfe8b     
**XRP**: rUocf1ixKzTuEe34kmVhRvGqNCofY1NJzV  
**LTC**: LesbjqB4eoT99r3yukxqyEAeYBdUMmkPDR  
**OXG**: oNXBrESwnUEddBqKE4sN96hWscwHtP8vjk
