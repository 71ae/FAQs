# Snode

[Snode (SND)](https://github.com/snodeco/snode-coin)

## Blockchain stuck

The Snode blockchain got stuck at block height 425167 on Nov 30th, 2019,
at 19:13 UTC.

### Repair

1. Back up your wallet.dat. It contains your addresses and keys.

2. Download the bootstrap file `snd-bootstrap-425787.zip`
[here](https://ufile.io/7jmmvf66) or [here](https://gofile.io/?c=Er4XbJ)
(MD5 Checksum f264ceba0e2b4f70541c04e3fc5003d4).

3. Stopp your Wallet application.

4. Locate your Snodecoin wallet directory on the filesystem of your computer.
It may sit in:
  * `~/.snodecoin/` on Linux
  * `~/Library/Application Support/Snodecoin` on MacOS
  * `%APPDATA%\Snodecoin` or `%APPDATA%\Roaming\Snodecoin` on Windows

5. Remove the following files and directories:
`banlist.dat`, `blocks`, `chainstate`, `sporks`.
You can delete `debug.log` as well,
especially if it became pretty big meanwhile.

6. Copy the bootstrap file into this Snodecoin directory and unzip it here.

7. Now you may re-start your Wallet application again.

It may take a while until the wallet finds suitable peers again
that are on the working chain. To watch this process open the
"Peers List" within the "Tools" menu. If it takes too long,
switch to the "Debug Console" and add a few nodes yourself:

* Open the [MNO Explorer](https://explorer.masternodes.online/currencies/SND/)
and write down a few Masternodes that recently got paid.
* Add a few of them, one by one, in the console:
`addnode 1.2.3.4 add` (replace the IP address with that from MNO)

This has worked for my Masternodes on my own VPSs, and finally
on the Desktop wallet as well.

But with few MNs live on the network they exceed their connection slots
quickly. The default is `maxconnections=125`, which apparently is not
enough.

### Masternode

If you are a mastenode owner, please add a line `maxconnections=1250`
or even with a higher number to your `snodecoin.conf` file and
restart your masternode. This will help the network to recover.


# Author

* [@71ae](https://github.com/71ae) - Andreas E.

If you find this helpful, a small donation always is welcome
(every coin helps):

- BTC 1Q1Hnm26TY3nf5NCxTcEJKMYq3C1ejTXCZ
- ETH 0x18eb62e93adceb68c8b28c7e0f6e168ad76500bc (ETH only, no ERC20 tokens)
- LTC LXNgnAodqT5HYBVqKpxdPKCdYFNRphMzg6
- ETC 0x502a5609fa5e0c1a991fbcc595a48385a764cd16
- ZEC t1XANY6JV8asAAUegv6v4S2bQE6SzAumkVQ
- ZIL zil19pa7mefxhal7jeda0p6agft5cxc97gfcnl55e0
- TRTT TCG38t9Zrjht41sErjDfS2wwn1hv64c5F5
- SND SUGGZeMNmTiuoXPxQ9XYbVATdoMyLWn4X8

# License
The content of this project itself is licensed under the
[Creative Commons Zero v1.0 Universal](https://choosealicense.com/licenses/cc0-1.0/) (CC0-1.0).

