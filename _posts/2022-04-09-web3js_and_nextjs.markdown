---
layout:     post
comments: 	true
title:      NextJS Web Front End
author:     YWS
date:       2022-04-09
categories: Learning
tags: 		Web3js NextJS ReactJS Tailwindcss
youtubeId: 	-340ucBEHx0
youtubeWidth: 550
youtubeHeight: 440
youtubeAutoplay: 1
description: "Hello people, This chapter is about react web ui and interaction with blockchain smart contract.
</br></br>
Let's learning together about front end web ui for our smart contract on evm compatible Blockchain with NextJS"
---


Hello people, This chapter is about react web ui and interaction with blockchain smart contract.

Let's learning together about front end web ui for our smart contract on evm compatible Blockchain with NextJS

# Web UI Front end using NextJS and Web3JS

In order to create the front end web ui we need several initial setup first

## NodeJS

Install npm first to your machine, so that you can install all the required framework using npm commands.
[Npm install package doc][npm-doc]

first go to this [page][npm-site] to install the nodejs to your machine.

## Initial setup for React Web3

The initial setup for web3 react front end is pretty simple.
Initial setup contain:
1. Nextjs
2. Web3js
3. Tailwindcss
4. @metamask/detect-provider

### NextJs setup
Currently in this section we are going to use a framework from react framework.

The name of that framework is [Nextjs][nextjs-site].
NextJs setup
```
npx create-next-app@latest your_apps_folder
```
replace `your_apps_folder` with your own folder, don't create the folder yet, it will create the folder for you.

### Web3Js setup

Web3js is a javascript library, a collection of library that allows you to interact with your deployed smart contract.
you can read the doc for more information [here][web3js-doc] 

so we need this library to use on our web3 front end creation.
Web3 setup
```
npm i web3@latest
```
as you can see, we always add `latest`, it means we want to pick the latest commit of web3 library to use.

### Tailwindcss

Tailwindcss is the styling that we are going to use in this section.
actually you can use whatever you want for styling the html,
this is only my personal recommendation,
so feel free to use another stylist css or maybe if you feel fancy you can create your own css.

Tailwindcss setup on NextJs
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
`cd` to your npm folder which you created before `your_apps_folder`
and do the command above.
the `npx tailwindcss init -p` is the command to initiate config of tailwind

go to your `tailwind.config.js`
```
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
modify it like above, but for this section, i guess you don't need components, you just need the pages.

go to your `globals.css` or if you don't want to make it global, we can create our own css like `your_pages.module.css`
so you can initiate your own css module later on your pages
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
add these 3 lines of code on your begining of line in your css.
notes: there will be a warning, let me know if you could make this warning disappear :(

Now you that already setup with the tailwindcss, to get familiar with the css name and property you can go to the doc [here][tailwindcss-doc]

### Metamask framework

For this is optional, you can use it or not is up to you.
just to make it easier to detect provider.

Metamask detect provider
```
npm i @metamask/detect-provider@latest
```
now you can execute it like this
```
const provider = await detectEthereumProvider()
if (provider) {
	try {
		await provider.request({ method: 'eth_requestAccounts' })
        const web3 = await new Web3(provider)
    } catch (err) {}
}
```
if you feel no need to use the framework.
we can have a little bit of changes in code like this
```
if (typeof window !== "undefined" && typeof window.ethereum !== "undefined") {
	try {
		await window.ethereum.request({ method: "eth_requestAccounts" })
        const web3 = new Web3(window.ethereum)
    }catch (err) {}
}
```

so feel free to change based on your need.



## Metamask Method explanation

For the metamask framework, we are going to use one methods.

1. get the metamask wallet account information
`window.ethereum.request({ method: "eth_requestAccounts" })`
or
`await provider.request({ method: 'eth_requestAccounts' })`


## Web3 Method explanation

For the web3 method, we are going to use some methods.

1. initiate the web3
`new Web3(provider)`
the provider is the detect provider from metamask framework or 
`Web3(window.ethereum)`
after you request to get the accounts

2. get the accounts to web3
`web3.eth.getAccounts()`
this will list the accounts you have that provider already passed to web3 when initialization.

3. set the contract to web3
To interact with corresponding deployed smart contract, after you deployed,
we need to give information to the web3.
```
new web3.eth.Contract(
        jumboSimulatorABI,
        "0x7660D1a823Ae70f9D309C4D62DC7Bfc18D4D98aE"
    )
```
as you can see above, we need to give ABI information and contract address on the blockchain.
abi you can get from remix ethereum IDE when you compile the contract.
or if you feel fancy enough, we can retrieve it using `truffle` framework to compile the contract as well.

4. interact with smart contract method

After we already pass our smart contract information to web3 framework.

Now we can start to call the methods and property through web3 framework.
here is the list of commands in our smart-contract jumbo simulator (of-course it depends on your smart contract method and property)
```
.....methods.deployer().call()
```
`deployer` is the public property in the smart contract, if you see carefully on our smart contract we have property called deployer.


```
.....getTotalSoldTickets().call()
.....methods.getTicketOwner(ticketID).call()
.....methods.getMyTickets().call({
		from: myWalletAddress
	})
```
as you can see about `call()`, we don't need to send the fee to blockchain and smart contract.
It just to read the smart contract. of-course each method and parameter is different, it is based on your smart contract when you create your own methods.

```
......methods.buyLotteries(ticketCount).send({
		from: myWalletAddress,
        value: web3.utils.toWei('0.0055', 'ether') * ticketCount
	})
```
for `send()`, it means the contract need to write the data, so we need to pay the blockchain fee such as gas fee, and also necessary fee for the tickets which is 0.005 ether.
as you can see there, we provide additional 0.0005 ether, the reason is because of gas fee, but actually you can do that without additional 0.0005, metamask will calculate it for you.

```
......methods.chooseWinner().send({
                from: myWalletAddress
                })
```
as you can see above, there is no gas limit or price provided as well, for some blockchain is fine like binance smart chain testnet, but some people recommended to give a value for calculation of gas fee between gas limit and gas price.
maybe this information will be usefull for you, to get latest block gas limit
`const lastBlock = await web3.eth.getBlock('latest')`
and then finally
`lastBlock.gasLimit`
and you can pass it to the send methods.
you can check more detailed info on this [doc][web3send-doc] about send method of web3.


# Conclusion

The method on web3 is not 100% will be same behavior on another blockchain, so probably better to encapsulate the method for each blockchain first, and setup the condition.
We need to provide different approach for each blockchain, probably in future it can be generic for all evm compatible blockchain like polygon, bsc, ethereum, etc.

Alright people, I guess that's all the info about web3.

please do let me know as well for any suggestion or maybe materials to improve on curcifer.tech

I would love to learn it as well from you guys / girls.

Thank you so much for reading and please visit the videos on youtube as well.

Have a good days!! :)


[npm-doc]: https://docs.npmjs.com/cli/v8/commands/npm-install
[npm-site]: https://nodejs.org/en/
[nextjs-site]: https://nextjs.org/
[web3js-doc]: https://web3js.readthedocs.io/en/v1.7.1/
[web3-git]: https://github.com/curcifer/share-knowledge/tree/web3_ui/smart%20contracts/dapps
[tailwindcss-doc]: https://tailwindcss.com/docs
[web3send-doc]: https://web3js.readthedocs.io/en/v1.7.1/web3-eth-contract.html#methods-mymethod-send