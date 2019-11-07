---
title: Decentralized power of Ethereum and IPFS
date: 2019-11-07T10:22:26.484Z
thumb_img_path: /images/ipfs-ethereum.png
excerpt: >-
  Blockchains are terrible at storing large amounts of data. Seriously, they’re
  really bad at it. For example, depending on the cost of Ether, you’re looking
  at a cost of hundreds (if you’re lucky) to [thousands of dollars per
  megabyte](https://ethereum.stackexchange.com/questions/872/what-is-the-cost-to-store-1kb-10kb-100kb-worth-of-data-into-the-ethereum-block)
  (MB) of data you put on Ethereum. But, see how **IPFS** rescues blockchain
  here.
template: post
---
<h1>The Decentralized Power of Ethereum and IPFS</h1>

<h2>How to Create Immutable Files:</h2>

<h1 data-breakpage>The Limitation of Blockchains</h1>

<p>Blockchains are terrible at storing large amounts of data. Seriously, they’re really bad at it. For example, depending on the cost of Ether, you’re looking at a cost of hundreds (if you’re lucky) to <a href='https://ethereum.stackexchange.com/questions/872/what-is-the-cost-to-store-1kb-10kb-100kb-worth-of-data-into-the-ethereum-block'>thousands of dollars per megabyte</a> (MB) of data you put on Ethereum.</p>

<p>To put this in perspective, the average size of a photo taken on my iPhone 6 is 2–3MB. Buying a car could cost less than adding the data for one photo onto the Ethereum blockchain!</p>

<h2><strong>Why are blockchains so bad at storing lots of data?</strong></h2>

<p>It takes a lot to duplicate data across thousands of machines. When a piece of data gets added to Ethereum, the new data becomes part of a block. This means that thousands of computers around the world are working together to verify that data by coming to a “consensus”. In the context of a blockchain, consensus means that these computers agree that the data for a given block is valid, and it’s okay to move onto the next block.</p>

<p>Because new blocks of data have to be verified by so many different computers all at once, there’s a limit to how much new data can be processed in a given block. At Ethereum’s current rate of 15 seconds per block, the average amount of data that gets put into a new block is around 20 KB. If we refer back to our photo size of around 2MB, it would take roughly 100 blocks for me to add that data to Ethereum. Additionally, that’s assuming I somehow managed to reserve 100 blocks of data all to myself (which realistically isn’t going to happen).</p>

<p>The above explanation is an extreme simplification of how Ethereum works. For more in-depth explanation, check out <a href='https://medium.com/@preethikasireddy/how-does-ethereum-work-anyway-22d1df506369'>this post</a> by <a href='https://medium.com/u/d446dafbe292?source=post_page-----e816e12a3c59----------------------'>Preethi Kasireddy</a>. It’s a great read.</p>

<h1 data-breakpage>What Blockchains Excel At</h1>

<p>The consensus process is what makes Ethereum so powerful. While we can’t add a lot of data to Ethereum at once, the consensus process assures us that all data added to the chain is immutable. Once data gets put onto Ethereum, it’s there forever. You can change the “state” of a blockchain by sending tokens or executing a smart contract, but the records of all previous states still exist in previous blocks.</p>

<blockquote><p><strong>Ethereum allows us to timestamp data in a way that prevents data tampering.</strong></p>

</blockquote>

<p>A few examples of where tamper proof, timestamped data time can be useful:</p>

<ul>

<li>Real world instrument measurements (<a href='http://blog.klaehn.org/2018/06/10/efficient-telemetry-storage-on-ipfs/'>telemetry data</a>)</li>

<li>Signed documents</li>

<li>Security photos / video footage</li>

</ul>

<p>But wait…if we think back to what we talked about earlier, these types of data would be incredibly expensive to store on a blockchain!</p>

<h1 data-breakpage>IPFS to the Rescue</h1>

<p><a href='https://ipfs.io/'>IPFS</a> helps solve a lot of problems on the modern web. It also solves a lot of problems for the new decentralized web! It turns out that by combining a blockchain with IPFS, we can timestamp much larger amounts of data than we’re able to using just the blockchain.</p>

<p>When data is added to IPFS, the protocol returns a hash of the data that was just added. <strong>This hash is cryptographically guaranteed to be unique to the content.</strong> If the same content is added to IPFS again, the same unique hash will be returned.</p>

<p><img src='https://miro.medium.com/max/60/1*_dzsD5VCQJ4JpPS4EOtXoQ.png?q=20' alt='img' referrerPolicy='no-referrer' /></p>

<p><img src='https://miro.medium.com/max/1978/1*_dzsD5VCQJ4JpPS4EOtXoQ.png' alt='img' referrerPolicy='no-referrer' /></p>

<p>Content retrieval using IPFS works in the reverse. To retrieve content that has been stored on IPFS, the same cryptographic hash returned from the storage process is provided back to the IPFS network. Through this retrieval process, the requester of the content is cryptographically guaranteed to receive the same content that was initially uploaded to the IPFS network.</p>

<p><img src='https://miro.medium.com/max/60/1*08WsJlt22_LNGRzPGfIA9A.png?q=20' alt='img' referrerPolicy='no-referrer' /></p>

<p><img src='https://miro.medium.com/max/1988/1*08WsJlt22_LNGRzPGfIA9A.png' alt='img' referrerPolicy='no-referrer' /></p>

<p>In other words, IPFS allows us to store data and then later retrieve it, with the knowledge that our data wasn’t tampered with. That’s pretty powerful.</p>

<p><strong>What’s even more powerful is when we combine this with Ethereum.</strong></p>

<p>Remember how blockchains allow us to timestamp data in a way that prevents data tampering? Also, remember how blockchains are really bad at doing this with large amounts of data? Well, now we can get around that limitation using IPFS.</p>

<p>Hashes provided back from IPFS are currently 46 bytes in size, which is 1/43478 the size of our 2MB photo from earlier. This means that an IPFS hash is magnitudes cheaper to store on Ethereum than the data itself.</p>

<p>So, if we wanted to timestamp a large piece of data, all we would have to do is upload that data to IPFS and then put the corresponding hash onto Ethereum.</p>

<h2>A Real World Example</h2>

<p>Let’s say that a company signed a rather large legal agreement. The signed PDF of that agreement was stored on IPFS and the corresponding hash was printed onto the Ethereum blockchain.</p>

<p>Now, let’s say there was a dispute where one party claimed the agreement had never been signed. This could easily be disproven by referencing the block where the hash of the agreement was added to the blockchain.</p>

<p>If all we had was the IPFS hash of the agreement, it could easily be claimed that the document was forged. After all, the document could have been added to the IPFS network at any time, not necessarily when the truthful party claimed it was. But, since the hash was added to the Ethereum blockchain at the time of upload to the IPFS network, the signed document was timestamped in a tamperproof way. And, because IPFS provides tamper-proof content retrieval, it can be proven that the content the hash points to hasn’t been altered in any way.</p>

<p><img src='https://miro.medium.com/max/60/1*QJ5e21hWKozOp7RXelZdZA.png?q=20' alt='img' referrerPolicy='no-referrer' /></p>

<p><img src='https://miro.medium.com/max/1878/1*QJ5e21hWKozOp7RXelZdZA.png' alt='img' referrerPolicy='no-referrer' /></p>

<h1 data-breakpage>Conclusion</h1>

<p>Blockchains like Ethereum and IPFS are both incredibly powerful tools. But, they both have their weaknesses.</p>

<p>Ethereum is really good at timestamping data but can only handle very small amounts of data at a given time.</p>

<p>IPFS is really good at storing data in a tamper proof way but there’s no way of proving when the data was added to the IPFS network.</p>

<p>When we combine Ethereum and IPFS, we gain the ability to timestamp any data we want, no matter how big the size.</p>
