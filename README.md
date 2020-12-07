# INSTALLATION PROCESS

First, we must download and install the newest Geth Tools and Software. This can be found on geth.ethereum.org.
The download address is: https://geth.ethereum.org/downloads/

Be sure to check wether you have a Mac or Windows OS, and wether it's 32 or 64-bit.

##### This is the version I downloaded for Windows 64-bit OS.

![Geth1](Screenshots/Geth1.png)

##### You'll want to download these tools into a master directory/folder.

![Geth2AfterUnzip](Screenshots/Geth2AfterUnzip.png)

## 1) GENERATING ACCOUNTS

To begin the network, we must generate two genesis nodes. When entering these commands, you'll want to work from the directory that has the applications in it.

cd into the directory, and run the following command:

`./geth --datadir MasterNode account new`

* "./geth" calls the geth application.
* The --datadir flag creates a directory for the node
* The third piece sets a name for your first node.
* The fourth piece establishes it as an account
* The fifth piece nominates that it's new.

After typing in the command, you'll need to create a password. The passwords provided are not recommended, because they're incredibly weak. The program will give you a public addresses for the keys.

COPY AND PASTE THESE SOMEWHERE. THEY'RE IMPORTANT

* FirstNodeName: MasterNode
* Password: admin
* Public address of the key: 0x5b02b4d444d5617455bf5dbdEe7446B6dBBFe723
* Path of the secret key file: MasterNode\keystore\UTC--2020-12-06T21-53-14.993467400Z--5b02b4d444d5617455bf5dbdee7446b6dbbfe723

`./geth --datadir zweiterKnoten account new`

* zweiterKnoten (second node)
* PW: german
* Public address of the key:   0x8130066e626fe4B9eA60675696802ee653194926
* Path of the secret key file: zweiterKnoten\keystore\UTC--2020-12-06T21-58-50.209494000Z--8130066e626fe4b9ea60675696802ee653194926

#### This is what the terminal will look like:
![Geth3Generating2NewAccounts](Screenshots/Geth3Generating2NewAccounts.png)
#### This is an example of a notepad with important information
![Geth4NotesAfterAcctGen](Screenshots/Geth4NotesAfterAcctGen.png)

## 2) Establishing the Network

Next, we'll want to establish the private network by linking it to the created genesis nodes. You'll need to create a name for the network, using all lowercase letters, no spaces, and no hyphens.

For this example, we'll be creating a Proof-of-Authority network (Clique).

The terminal will look similar to the following picture:

![Geth5GeneratingGenesisBlock](Screenshots/Geth5GeneratingGenesisBlock.png)

![Geth6ExportingGenesisConfig](Screenshots/Geth6ExportingGenesisConfig.png)

## X) INITIALIZING EACH NODE

`./geth --datadir MasterNode init zbankdeutschland.json`
`./geth --datadir zweiterKnoten init zbankdeutschland.json`

## X) BEGIN MINING BLOCKS

##### NOTE:
    The "enode: ADDRESS " portion of the second command may be different.
	Be sure to look for the address in the first terminal, upon the initialization
	of the mining of the first block.



#### COMMAND FOR TERMINAL 1

./geth --datadir MasterNode --unlock "5b02b4d444d5617455bf5dbdEe7446B6dBBFe723" --mine --rpc --allow-insecure-unlock

#### COMMAND FOR TERMINAL 2

`./geth --datadir zweiterKnoten --unlock "8130066e626fe4B9eA60675696802ee653194926" --mine --port 30304 --bootnodes "enode://32bd48689bd15e40f214e83c5c2882b034fdde0c849cb502b81dc7793f506c38afb6c08b38317371778e85b4c65dd5afb5dd59639c92f1ec8bfa1103786ec6f2@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock`

![Geth7DeletingHarmonyFile](Screenshots/Geth7DeletingHarmonyFile.png)
![Geth8InitNodeswGenJsonFile](Screenshots/Geth8InitNodeswGenJsonFile.png)
![Geth9MiningCodes](Screenshots/Geth9MiningCodes.png)
![Geth91PrivatePoARunning](Screenshots/Geth91PrivatePoARunning.png)
![Geth92Connected](Screenshots/Geth92Connected.png)
![Geth93FirstAccountRich](Screenshots/Geth93FirstAccountRich.png)
![Geth94SendingMoney](Screenshots/Geth94SendingMoney.png)
![Geth95SendingOneJeffBezos](Screenshots/Geth95SendingOneJeffBezos.png)
![Geth96StatusBox](Screenshots/Geth96StatusBox.png)
![Geth97SentTransactionFullStatus](Screenshots/Geth97SentTransactionFullStatus.png)


---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
