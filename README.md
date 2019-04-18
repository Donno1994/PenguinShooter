# PenguinShooter - A Lightning Network enabled RPG which displays LN invoices within the game.
It is a simple demo RPG in which you fight monsters and lvl up.
You will see LN invoices as QR codes in the game and scan them with your mobile wallet or click them which copies it to clipboard for fast desktop payments (for example with Zap wallet)


You can open a door, spawn monsters, buy items etc. with small Lightning Network payments.
https://www.youtube.com/watch?v=ZCOwVHUmIT4

In this version you can now connect to your own LND node which makes it basically free. You can also connect to a testnet node.
By default you will be connected to my personal (mainnet) node 02b94191cd26b1b8650b1204371ee65aa8725ca56474efbb629240a41d4bf7fec0@penguinshooter.chickenkiller.com:9735

This is also a demo game to show how livestreaming could become more interesting.
You can setup a webserver which creates invoices to your livestream viewers.
When they pay these invoices, something will happen live in your stream. Some payments help you (e.g. buy you items) and some are bad (e.g. freeze you for some seconds). If you are connected to your own node, you as the streamer can keep that money that you earn while playing.

Link to the webserver https://github.com/Donno1994/PenguinShooterWeb

Medium article of livestreaming features https://medium.com/@BR_Robin/user-intervention-in-livestreams-via-ln-penguinshooter-5e12bdcece49

Video Examples: https://www.youtube.com/watch?v=gTuWi-WNynQ&t=1s


To play this game you need a Bitcoin Lightning Wallet. To setup a LN node on a Raspberry Pi, follow this guide https://github.com/Stadicus/guides/blob/master/raspibolt/README.md .
If this is to hard for you, you can use https://bluewallet.io/ as a custodial solution.
You also need a windows computer.

To connect this game with your own node, you need the LND implementation of LN https://github.com/lightningnetwork/lnd
Important are the invoice.macaroon and tls.cert



## Instructions to play this game (connecting to the LN node of the developer)

1. Download this repository.
2. Open the PenguinShooter-master folder and run PenguinShooter.exe
The game will now boot and connect to my LND node. If successful, it will display a QR code at the wall in front of you.
3. You now have to pay the invoice at the wall (150 sat). You can either use your mobile wallet and scan the QR code, or you can click on the QR code (which copies it to clipboard) and paste it into a desktop LN wallet.
4. For gameplay visit https://medium.com/@BR_Robin/a-bitcoin-lightning-network-powered-rpg-penguinshooter-6d36cc34de0c

## Instructions to play this game with your own node (testnet and mainnet possible)
1. Download this repository
2. Enter the folder PenguinShooter-master\PenguinShooter_Data\Resources and open the donner.conf
3. Enter the information about you LND node. Replace "penguinshooter.chickenkiller.com" with the IP address of your node. If it is on the same computer as you run the game you can enter "127.0.0.1". If it's in the same wifi network (e.g. if you have the node on a rapberry pi) you can use something like "192.168.2.157" (you need to check the local IP address of the node). Under "Port" enter the port number of your LND node (default is 10009).
4. Copy your invoice.macaroon and your tls.cert into the same folder as donner.conf. You can find this in your LND folder under ".lnd/data/chain/bitcoin/mainnet/invoice.macaroon" and ".lnd/tls.cert"
5. Start the game and see the instructions above (connecting to developer node)

If you want to test the webserver which generates a normal internet webpage and generates invoices, check out https://github.com/Donno1994/PenguinShooterWeb
If you want to test livestreaming, you can connect your own node and keep the money that you earn.
I know, this game is not the most interesting one, but I hope it's a nice demo on how livestream viewer integration could work with Bitcoin Lightning Network.

This project was made by https://twitter.com/BR_Robin and the Unity Game Engine.
I used the open source API from https://twitter.com/sputn1ck from https://www.donnerlab.com/ . You can find that API on https://github.com/donnerlab1/donnerunity/
Also check out his LN powered game when he plays donnerdungeon live on https://www.twitch.tv/donnerlab (checkout his twitter for the exact times)

I am a hobby developer who works on this project in his spare time. I created this game for fun to show the use cases of LN in games.
The game itself has some flaws. My LN node might be offline or payments could go through but you see nothing (hopefully it doesn't happen)
If you find bugs or have some other criticism, you can use the issue function on github. I will try to fix them.

If you have some ideas that I could implement, let me know.
I am especially interested in new features that the viewers can pay to help or annoy the streamer.

I hope you enjoy this game and can already see how the Lightning Network can completely change the gaming industry.
