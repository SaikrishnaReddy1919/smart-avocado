---
title: Components to interact with Ethereum
date: 2020-10-03T09:13:56.627Z
thumb_img_path: /images/1.png
excerpt: You need 2 main components to interact with Ethereum network . 1.) Web3
  instance and 2.) A Provider.
template: post
---
1. **Web3 Instance**

It's a javascript framework that acts as a middleware between you and an Ethereum node. It transforms JS commands into JSON-RPC requests. **web3.js** and **ether.js** provide Web3 instances that can be used either in browser or in console (e.g. Truffle).

2. **Provider** 
A provider is technically an Ethereum node. You can run it on your computer (e.g. Ganache, Geth, Parity) or get it as a service (e.g. Infura). Web3 Instance is given provider's endpoint (Ip/Port) as a parameter in order to submit JSON-RPC requests.

In this case:

**JavaScript VM**:

* Web3 Instance is injected by Remix --> web3.js
* Provider is supplied by Remix ---> A Js based Ethereum test node runs in the browser,

**Inected Web3**:

* Web3 Instance is injected by MetaMask --> web3.js
* Provider is connected to MetaMask ---> You select the network in the menu (main/ropsten/kovan...) or enter endpoint of a custom node

**Web3 Provider**:

* Web3 Instance is injected by Remix --> web3.js
* Provider is connected to Remix ---> You enter endpoint of a custom node

------

* Javascript VM: It will run an isolated ethereum node in the browser. It is very useful when you want to test a contract.
* Injected Web3: It will try to use the "Web3 provider" embedded in the browser. For example MetaMask extension will embedd a "Web3 provider", you can configure to connect that provider to a testnet or to mainnet. This allow to interact with a real network.
* Web3 Provider: It will ask for you to supply the RPC address of a ethereum client. This provides maximum control, you connect to your own node. For example a geth or parity instance.

Since MetaMask allow to use your own "Web3 Provider" the last two have similar functionality. One important difference is that MetaMask will handle account managment and for "Web3 Provider" you will have to manage them from the client.

Adding on to this.. extensions like MetaMask or dApp enabled browsers literally inject a web3 instance into the javascript on the page. Your dApp javascript code can use this instance, or more correctly, use the currentProvider of the web3 instance to initialize your own applications web3 client library.

------
**Some images for better understanding above concept:**
![](https://cdn-media-1.freecodecamp.org/images/1*sd62aH6GGS1RoCR9t4QNyQ.png)

![](https://media.springernature.com/original/springer-static/image/chp%3A10.1007%2F978-1-4842-4075-5_5/MediaObjects/470312_1_En_5_Fig1_HTML.jpg)

****