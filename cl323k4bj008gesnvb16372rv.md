## Interplanetary File System(IPFS)- 

A GATEWAY TO A DECENTRALISED STORAGE SYSTEM.



File sharing, therefore, is much more than a technical term: it is a linguistic
and conceptual hinge that both locks together, and enables movement between,
the technical, discursive, and institutional dimensions of contemporary digital
culture.

It is a phenomenon as old as the World Wide Web. Even when the internet was tiny and only a handful of people were using it – file sharing was already very common. Thousands of users were sharing images, books, and songs.
The term file sharing can be used interchangeably with a storage system because both serve the same purpose of holding data and also have the ability to share the same 
Data.
In this article we will talk about the concept of Interplanetary File System (IPFS), a decentralised file system for building the next generation of the internet.

# What is an Interplanetary File System?

IPFS is a decentralised storage and delivery network which builds on fundamental principles of P2P networking and content-based addressing for storing and accessing files, websites, applications, and data.
Today's World Wide Web is structured on ownership and access, meaning that you get files from whoever owns them — if only they choose to grant you access. 
IPFS operates in a different structure that is based on the idea of possession and participation, where many people possess each others' files and participate in making them available.

## How does IPFS work?
One of the most important differences between the centralised web and the decentralised web is the way we store, identify and retrieve data on each.
IPFS uses two strategic and widely used principles to build upon each other to enable the IPFS ecosystem.
The two fundamental principles to understanding IPFS includes: 
- Content addressing and Unique identification.
- Content discovery through distributed hash tables.

### Content addressing and Unique identification

Let's use a simple example to illustrate:
Two of your friends wants to use your PC to find a document at different time intervals, you described to friend A to go the your  ```
C drive``` click on the ‘Users’ folder, thereafter click on the ‘SOPHIA’ directory, then you'd find the ```
Downloads ``` folder inside the folder you will see another folder called ``` aaronproject ``` click on it, inside your ```
"aaronproject"
``` you’ll see ```
Ernest project
``` folder, inside it you will then find the ``` mathupwork.pdf ``` document. 
To friend B, you simply instructed your friend to navigate to the search bar and type the ```
mathupwork.pdf``` document and boom the document shows up.

One of your friends identified the book by its **location**, and the other by its **content**.
**Friend A** used the location strategy commonly used in a centralised network such as ```
C:\Users\SOHIA\Downloads\aaronproject\Ernest project\mathupwork.pdf
```
While **friend B** used a **unique content addressing method**. 

IPFS uses content addressing to identify content by what's in it rather than by where it's located. Looking for an item by content is something you already do all the time.
When you add a file to IPFS, your file is split into smaller chunks, cryptographically hashed, and given a unique fingerprint called a content identifier (CID). This CID acts as a permanent record of your file as it exists at that point in time.
When other nodes look up your file, they ask their peer nodes who's storing the content referenced by the file's CID. When they view or download your file, they cache a copy — and become another provider of your content until their cache is cleared. 
This means that files stored on IPFS are resistant to tampering and censorship — any changes to a file don't overwrite the original, and common chunks across files can be reused in order to minimise storage costs. 
Many distributed systems use content addressing through hashes as a means for not just looking up for content, but also binding it together — everything from the commits that back your code to the blockchains that run cryptocurrencies leverage this strategy. However, the underlying structures in these systems are not necessarily interoperable.
For more info [InterPlanetary Linked Data (IPLD)](https://ipld.io/)


### Content discovery through distributed hash tables

IPFS uses a distributed hash table, or DHT. A hash table is a database of keys to values. A distributed hash table is one where the table is split across all the peers in a distributed network. To find content, you ask these peers.
The libp2p project is the part of the IPFS ecosystem that provides the DHT and handles peers connecting and talking to each other. (Note that, What makes libp2p especially useful for peer-to-peer connections is connection multiplexing.)
Once you know where your content is (or, more precisely, which peers are storing each of the blocks that make up the content you're after), you use the DHT again to find the current destination of those peers (routing). So, to get to the content, use libp2p to query the DHT twice.

In programming, data structures are everywhere. The way you organise data into variables in order to use them in programs involves anywhere from dozens to millions of data structures. If you're a developer, you're probably familiar with common data structures like arrays, objects, graphs, etc. These structures are often linked together: for example, in a common data structure known as a linked list, each item indicates where to find the next item in a computer's memory. That, is in fact what the protocol uses.

On the decentralised web we access data directly from our peers, rather than from a central authority. Within an isolated environment, such as your own laptop, you can have a great degree of trust in the data structures you work with in memory or on disk. However, in a decentralised system you have less, or possibly zero, trust among peers. To fit this environment, we need an efficient way to link data structures together, while still preserving our ability to verify their integrity (a crucial property of CIDs). To continue the previous example, if we're traversing a linked list that we got from the distributed web, we don't want a bad actor to be able to insert items in the middle undetected.

## Benefits of  IPFS in blockchain

**Decentralisation**

One of the major benefits of IPFS is Decentralisation - Making it possible to download a file from many locations that aren't managed by one organisation:
Supports a resilient internet. If someone launches a DDOS attack on Instagram's web servers or an engineer at Instagram makes a big mistake that causes their servers to catch fire, you can still get the same web pages from somewhere else. How?
IPFS only works well when people are actively participating. If you use your computer to share files using IPFS, but then you turn your computer off, other people won't be able to get those files from you anymore. But if you or others make sure that copies of those files are stored on more than one computer that's powered on and running IPFS, those files will be more reliably available to other IPFS users who want them.
Other benefits include **Speed, Scalability, Security, Efficiency**.

### Who uses IPFS?
- Researchers
- Archivists
- Content creators
- Blockchain developers
- Offline users
- Service providers.

**Summary**
The concept of IPFS was developed to tackle the setbacks encountered in storing large files in the blockchain ecosystem. IPFS is a file sharing system that can be leveraged to more efficiently store and share large files. It relies on cryptographic hashes that can easily be stored on a blockchain.
Using IPFS is quite remarkable and understanding the technical wizardry that makes it possible is even more exciting. If successful, IPFS and its complementary protocols could provide resilient infrastructure for the next generation of the web. The web that was promised to be distributed, secure, & transparent.

***Sources***


Comer, Douglas. Computer networks and the internet. Pearson, 2015. goo.gl/AbM8st/

IPFS whitepaper https://docs.ipfs.io/concepts/what-is-ipfs/#decentralization/




**#programming #thw-web3**


