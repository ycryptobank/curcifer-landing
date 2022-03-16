---
layout:     post
title:      Blockchain wallet, Smart contract, ERC20
author:     YWS
date:       2022-03-16
categories: Learning
tags: 		Blockchain
youtubeId: 	p7MjFW8KTEg
youtubeWidth: 550
youtubeHeight: 440
youtubeAutoplay: 1
description: "Hello people, This chapter we will code an interesting smart contract for Jumbo Lottery Simulator.
</br></br>
Let's learning together to create smart contract on evm compatible Blockchain with Solidity<br/>"
---

Hello people, This chapter we will code an interesting smart contract for Jumbo Lottery Simulator.<br/>
Let's learning together to create smart contract on evm compatible Blockchain with Solidity.<br/>
First before we begin the journey to code the smart contract,
we need to know first about the wallet.


## Wallet
---
Blockchain Wallet / Crypto Wallet

In order to interract or transact in the blockchain, we need a wallet to store our cryptocurrencies.

there are 2 types of wallet that I know so far:

1. `Custodial Wallet`
2. `Non-Custodial Wallet`


## Custodial Wallet
As the name mentioned, the wallet is managed by the 3rd parties.

So if anything happen to your wallet,
you can have many action provided by your wallet provider, such as freeze account, recover account, transaction report, etc.

Pros:
- Easy to use
- Provide many blockchain
- Many cool feature like defi, borrow, lending, exchange, etc.
- Support available

Cons:
- you put your key to the wallet provider to manage it for you, so if the company broke or hacked, sometimes you will lost your funds as well.
- recovery wallet sometimes very tedious work to do, sometimes need to wait from support.
- need to input various information, such as, ekyc, phone number, email, etc.


## Non Custodial Wallet
Also as the name mentioned, the wallet will be managed by you only, no 3rd parties going to manage it for you.

The Non Custodial wallet is like `you on your own`, we have responsibility to secure our own data, keys, etc.

There is no perfect Application, all also contain bug.
but for non custodial wallet, as long as you save your key securely, if something happen on your wallet, you will still can recover to any wallet.

Pros:
- Provide many blockchain too (for some wallet like MM)
- Can recover wallet anytime anywhere if you have your mnemonic phrases.
- can recover account anytime anywhere if you have your private keys.
- Customize Network and many more (depends on the wallet)
- Can be used directly, no additional private info need to input (email, password, ekyc, etc)

Cons:
- Need little bit knowledge to use
- Support only available for wallet related software (bug, ui, crash, etc).
- No transaction report (Usually for reporting tax).
- You will responsible for your own security.


It depends on your need, wise people will use both of them to action.

also if you know about `cold-wallet` and `hot-wallet`, both of them also have types like explained above.
`cold-wallet` non-custodial
`hot-wallet` custodial
`hot-wallet` non-custodial

but I feel some `cold-wallet` is also custodial (let me know if you found custodial part of cold-wallet xD)

so I hope not confusing you, please give me your opinion too :)

---

<br/>
### Alright I guess we know little bit about what is wallet.
# Smart Contract
---
Smart Contract

The Smart Contract is actually a simple program that written on blockchain to execute transaction or interraction with the blockchain based on predetermined condition and verification.

There are many language to write smart contract which is:
- Solidity
- Rust
- Vyper
- Yul
and many more.

each of language has it's own pros and cons, so you can choose one is the best for you.
currently I am comfortable using Solidity, since first time learning about smart contract programming.

In this chapter we are going to code smart contract with Solidity.

## Notes

If you see carefully when scanning smart contract in a blockchain.
Smart contract looks the same like your wallet when you scan on blockchain.
have its own wallet, tt can store cryptocurrency.

so basically it is same, only the way to interract with blockchain is based on the code written in the smart contract.

Only It is speedy, efficient, and accurate, since it is automatically do action whenever you trigger their methods that you just wrote or read.
There are no intermediates when handling transaction, secured, and transparent.
Anybody can see the transaction or any action did by smart contracts.

also before you invest to some defi with smart contract, if you are programmer, make sure there are no malicious code inside the contract (I guess this is the privilege of being a programmer xD)

---

<br/>
### about the famous ERC20
## ERC20
---
ERC20

Based on what I see when scanning the ERC20 token contract.
Overall they are also smart contract.

A special smart contract which conform the protocol of ERC20 on their corresponding blockchain.

if you know about ERC-721 (NFT) which stand for `Non-Fungible Token`, ERC20 token is `Fungible Token`
mean 1 token represent the same value as other token.

Basically all of it is a smart contract conforming the protocol of corresponding standard in each blockchain.

In this chapter Also I will show you little bit about ERC20.

## Notes

Do you know about `ERC-1151`?
this token is sometimes famous to create in metaverse gaming.

Creating in game property like Weapon, accesories, etc.

NFT like but it is `Non-Fungible` but also `Fungible`...
So what should we call this? semi non fungible token? xD

Give me your opinion on Curcifer Tech Twitter :)
I will reply ;X

---

Please also Check The Videos for more detail.


Ref:
- Smart Contract Tutorial
- Custodial (gateio, matrixport, cryptocom, bitflyer, exodus)
- Non (MM, TrustWallet)
- IDE



Okay People, See you on next chapter of Curcifer Tech Channel
