Dash Paper Wallet Sweep Procedures v1.0
=======================================

The latest version of this document is available at https://github.com/rstms/paper-wallet-procedures/blob/master/dash-sweep-procedures.md
For further information please contact the author via github.



Barcode To PC
-------------
To avoid errors transcribing your paper wallet keys, one good choice is to use a QR reader application.  BarcodeToPC is a client/server system that uses a smartphone app and a PC server to allow you to scan a QR code's data directly into an input field on a program running on your desktop.  You can use it to scan a public key into a blockchain explorer page open in your browser, or to scan a private key for input into your wallet program.

### Install Barcode To PC Server
On your desktop, go to https://barcodetopc.com/ and install the server program.

### Install Barcode To PC Phone App
On your phone, go to the browser and open https://barcodetopc.com, then use the links to the Play store or the App store to install the app


Install Dash Wallet on Desktop Windows System
-------------------------------------------------
### Install the Dash Wallet Software from www.dash.org
As of 2017-04-06, the latest Dash Core version for a Windows 10 PC is:
https://www.dash.org/binaries/dashcore-0.12.1.4-win64-setup.exe

Install and run the program

### Use Default Install Directories:
 - Wallet Program: ```C:\Program Files\DashCore```
 - Wallet Data: ```C:\Users\[USER_NAME]\AppData\Roaming\DashCore```

Once the program is started, you may want to wait for the blockchain to load.

### Open the Debug Console
In the DashCore program's main menu, choose Tools->Debug Console
In the debug console's input field, type
```
importprivkey 
```
Enter a space after ```importprivkey``` and use the Barcode To PC program to scan your paper wallet's private key.
Hit Enter, and your paper wallet has been swept.

Verify Wallet Value
-------------------
Dash Core will now search its copy of the blockchain for references to your wallet address.  Wait for the popup 'Rescanning...' window to close and you will see the DashCore balance update to include the value of your swept wallet address.

Your wallet is now available to supply value to send transactions created with the DashCore program.
