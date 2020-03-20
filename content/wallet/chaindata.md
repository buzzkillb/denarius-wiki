---
title: "Chaindata"
date: 2020-03-05T00:16:05-08:00
---
### Sync Denarius Wallet Fast
{{% notice warning %}}
Always backup **wallet.dat** to a safe location.
{{% /notice %}}

To sync your new Denarius QT Wallet or denariusd faster, download chaindata.zip from here

https://denarii.cloud/

Then unzip the **chaindata.zip** file to your Denarius data directory.

#### Data Directory Locations

| OS | Data Directory |
| ------ | ----------- |
| Windows | C:/Users/yourname/AppData/Roaming/Denarius |
| macOS | /Library/Application Support/Denarius |
| Linux | ~/.denarius/ |

#### Unzip Windows
![Image](https://denariustalk.org/uploads/monthly_2018_03/roaming-folder.png.077148e27eb63de46e21e45a6f52dbfd.png)

#### Unzip Linux

```
cd ~/.denarius
rm -rf database txleveldb smsgDB
wget https://denarii.cloud/chaindata.zip
unzip chaindata.zip
```

#### Start Wallet

Run the native QT Wallet or denariusd after extracting the .zip and you will sync to the current block height fast.

If you get an error when starting the QT or denariusd, go to the database folder and delete the files inside, and restart the wallet. Also ensure you run 
```
./denariusd stop
```
to stop the denarius daemon if running before unzipping chaindata.

Use **7zip** for Windows unzipping. https://www.7-zip.org/download.html

reference: https://denariustalk.org/index.php?/topic/157-sync-denarius-fast-any-os-chaindatazip/
