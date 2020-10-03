---
title: What are MERKLE TREES?
date: 2020-10-03T09:30:22.022Z
thumb_img_path: /images/merkletree-min-1024x512.png
excerpt: Simply, a Merkle Tree is a data structure that allows us to make
  efficient verifications that data belongs in a larger set of data.
template: post
---
Quite simply, a Merkle Tree is a data structure that allows us to make efficient verifications that data belongs in a larger set of data.

They are commonly used in Peer to Peer networks where efficient proofs of this nature will help increase the scalability of the network.

Let’s take a step back and take a look at a binary Merkle Tree from a high-level. A Merkle Tree is a collection of hashes reduced to a single hash:

![](https://hackernoon.com/hn-images/1*UrjiK3IjdbgoV2dyKRvAGQ.png)
 We use letters for convenience in this illustration. Each single letter represents a hash. The combined letters represent concatenated hashes that have been combined and hashed to form a new hash.

Over a series of a steps the four leaf hashes A, B, C and D are combined to create a single, unique hash that allows us to quickly check for inconsistencies without having to look at each individual data point.

As peers in a system, I can simply ask if your root matches mine. If so, we agree. This is a nice optimization for distributed systems of any kind!