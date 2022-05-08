---
layout:     post
comments: 	true
title:      Profitable Pulsar Blockchain
author:     YWS
date:       2022-05-08
categories: Learning
tags: 		Pulsar Review Blockchain Investment
youtubeId: 	TzyBhgbeP74
youtubeWidth: 550
youtubeHeight: 440
youtubeAutoplay: 1
description: "Hello people, Let's earn some little profit from our idle CPU.
</br></br>
In this chapter we are going to review Pulsar blockchain, especially on how can we make use of our idle CPU to get the coin"
---

Hello people,

it's been a very busy days, i am sorry for not post any materials sooner.

Today I want to introduce my latest finding on new blockchain called `PULSAR`.

The main coin / token on this blockchain is PLSR coin.

It was just recently launch on market 2022 based on the web description.
The good thing about Pulsar is that, it's doing both consensus which is `Proof Of Stake` (POS) and `Proof of Work` (POW),
as you know already about what is POW, this coin is mineable, you can mine it with CPU,
also with POS, you can just simply save / store your coin to your wallet and let it sit there, 
you eventually will get a chance to win a rewards of POS in PLSR coin.

And there you go, double profit :)
I guess recently some other coins also doing something similar like thi, but I found out that PLSR still young and can grow in many ways (Let's support the community as well).

Let me explain about our roadmap today:
```
- Setup Pulsar Wallet
- Mining setup with Windows
- Mining setup with Mac
- POS on wallet
- Liquidation
```


## Setup Wallet
- Let's download the wallet app on the github [here][wallet-git]
- Install it to your desktop 
- After successfully install you will see it trying to sync the blockchain, leave it like that until synced 100%, I recommend you to use external HD and customize your blockchain data to store it inside your external HD instead of your desktop drive, since it will take too much spaces.
- if it already synced, we can go to `Receive` transaction Tabs.
- in `Receive` section, name the label whatever you wish, for ex: `miningwallet`
- no need to input amount or change currency, just tap `Request Payment`
- you will see new address created on the list below your form input, if it done correctly, you will see something like this
<img src="/assets/May2022/wallet-detail.png" width=516px height=370px />
- you can also double tap the wallet address info to see the image and detailed info again if you close it.
<img src="/assets/May2022/wallet-list.png" width=513px height=155px />
- now copy using `Copy Address` button in detail info.
<img src="/assets/May2022/wallet-detail-explain.png" width=516px height=370px />

### Congratulation, now you got your own working pulsar wallet.
You need the wallet address to put it on the mining script later.

<br/>
## Mining setup with Windows
- There are several executable or application to mine but for now let's use [SRBMinerMulti][srbminer].
- download the zip file from the latest releases.
- inside SRBMinerMulti make find the `.exe` file.
- go to it's properties and set `Run as Administrator`.
- don't forget to allow the file through your windows defender or anti-virus, it will report as trojan-horse, because it trying to manipulate your OC and it also has a feature to modify remotely, so the anti-virus will detect this as Trojan horse, since it behave same way I guess.
- now find `start-mining-pulsar.bat`.
- Edit file, it will ask for your permissions if it first time you edit the bat file, just choose `Run anyway`.
- Delete the line before `Srbminer`, it should be like this below.
```
SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum-eu.rplant.xyz:7030 --wallet your-wallet-here
```
- let's add your miner wallet, remember we already have wallet address for PLSR, so let's add it to script
```
SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum-eu.rplant.xyz:7030 --wallet PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV
```
- this is optional but I think the pool that we are trying to use need worker name which is our miner name, so let's add it by `.your-worker-name`, in this case i will name it as `myminer`.
```
SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum-eu.rplant.xyz:7030 --wallet PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer
```
- now depends on your CPU capabilities, if your cpu like 16 cores, 32 threads like mine, and want to utilize it like 30 threads for mining, we can do like this
```
SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum-eu.rplant.xyz:7030 --wallet PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer --cpu-threads 30
```
- based on the mining pool, in this tutorial we are using [rplant pool][rplant], and we will use `webpassword` feature to secure the miner.
```
SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum-eu.rplant.xyz:7030 --wallet PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer --password webpassword=ppww --cpu-threads 30
```
as you can see above I set the password `ppww`, means if I want to update any property like `minimum payout` on pool, I will need to `Set` the password same like above miner webpassword, if not same it will be rejected.
- let's check our location and pool location, we better to use the nearest location in order to have better connection. In my case I am in asia-pasific region.
```
SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum+tcp://stratum-asia.rplant.xyz:7030 --wallet PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer
```
we can just copy from the miningpool url, in this case i am using [rplant mining pool][rplant]
- lastly, you will need to update little bit like this.
```
C:\\Downloads\\RBMinerMulti-0.9.4-win64\SRBMiner-MULTI.exe --disable-gpu --algorithm curvehash --pool stratum+tcp://stratum-asia.rplant.xyz:7030 --wallet PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer
```
depends on your location, don't copy paste above since your `SRBMiner-MULTI.exe` file is different then mine.
easiest way it just open properties and copy the location, paste it to your bat file script `your-srbminerexe-location\SRBMiner-MULTI.exe`
the reason why we need to do this is because we want to run the bat file as administrator
- okay you are done with the setup, save, close, and now right click the corresponding bat file and choose `Run as Administrator`.

### Congratulation!! Now you are mining pulsar coin on Window :)

- Download the latest cpuminer application script on [github releases][cpuminer].
- The same way like above we just need to edit the script file, in this case is the bash file.
- before doing that, let's run the cpuminer script 
```
./cpuminer-sse2 --help
```
you will see security complain
go to setting -> security and privacy
<img src="/assets/May2022/security-mac.png" width=334px height=146px />
select `Allow anyway`
- now, let's edit the bash file `miner-pulsar.sh`
- actually rplant mining pool already make it easier for us to just copy paste the commands, so just go to [here][rplant], navigate to `pulsar`
- on Pulsar section, go to `Connect` 
<img src="/assets/May2022/connect-pulsar.png" width=480px height=216px />
- below you can find the script generator
<img src="/assets/May2022/connect-pulsar.png" width=428px height=157px />
choose whatever work with you and copy the script
- now go back to your bash file, delete all and paste the script.
```
#!/bin/sh
while [ 1 ]; do
	./cpuminer-sse2 -a curvehash  -o stratum+tcp://stratum-asia.rplant.xyz:7030 -u PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer -p webpassword=ppww
	sleep 5
done
```
as you can see we still missed another parameter which is threads, because we don't want to use all our CPU resource to mine, unless you wish like that then its fine.
- to customize the threads usage
```
#!/bin/sh
while [ 1 ]; do
	./cpuminer-sse2 -a curvehash  -o stratum+tcp://stratum-asia.rplant.xyz:7030 -u PHLf2R7sEh8t2y1baZS853AThQvoYHLFtV.myminer -p webpassword=ppww --threads=4
	sleep 5
done
```
since my mac is quad core i7, I guess it should be able to run up to 8 threads, but 4 threads is the stable one.
### Disclaimer -> it may burn your mac CPU, so please consider the risk to use it for long term mining.
- now run the bashfile `./miner-pulsar.sh`, you will asked a few question from mac security, and select `open`.

### Congratulation, now your are mining pulsar coin on Mac :)

## POS on wallet
- If you watch the video, I will skip to the part of POS explanation.
- after download and synced wallet.
- make sure your wallet is unlocked, you can check by go to `Setting` tab.
- yes just that, pretty simple huh? you already participate on POS just by holding PLSR coin on your wallet, you will need internet connection and turn ON tho, if Offline, you won't get any rewards.

## Liquidation

To liquidate the PLSR to your own real life currencies, you will need to do several steps.
I am using exbitron and local exchange to do this.
Exbitron exchange is quite easy, you don't need to upload any ekyc or whatsoever.
Just register, go to wallet section, search for `PLSR`.

After you found PLSR you will see the exchange wallet, send your some PLSR from your wallet to exbitron wallet.
Go to PLSR/LTC market, I recommend you to do this because its cheaper, but its up to you.
exchange to LTC, withdraw your LTC to your local exchange, in this case my local exchange is [bitflyer][bitflyer].
Send LTC from exbitron to my local exchange LTC wallet.
Trade LTC to Local currencies, in my case is YEN.
Finally Withdraw to bank!

### Congratulation!! now you already liquidate your mining result!

# Disclamier
if you have so much funds on crypto, beware of the tax tho :)
This materials is only for experiment and learning purposes
Not a financial advice, just an FYI.

# Conclusion

Pulsar blockchain has a future to compete with other cryptocurrencies.

By looking at the security and scarcity of the data, it supported by not just mining but also with POS on every wallet.

So if hacker attack the Pow Node on mining pool, it still have POS on every core wallet of client, there is almost impossible to attack all of user core wallet compare to only POW coin.
This is the combination of it, so what do you think? :)

Its easy and can gain much profit just by holding the coin.
By mining and holding it on your core wallet, I guess you already indirectly support the network of pulsar coin.
So, what do you think of this new blockchain?
Let me know your thought :)

Please drop your love on the [video][videos] as well. it really meaningful for me.
The details on the videos too :)

Alright, see you on the next chapter on Curcifer Tech.
Hope you have a great and profitable days!!















[wallet-git]: https://docs.npmjs.com/cli/v8/commands/npm-install
[srbminer]: https://github.com/doktor83/SRBMiner-Multi/releases
[rplant]: https://pool.rplant.xyz/
[cpuminer]: https://github.com/rplant8/cpuminer-opt-rplant/releases/
[bitflyer]: https://bitflyer.com/en-jp/
[videos]: https://youtu.be/TzyBhgbeP74