# Whitepaper

(draft). Please note currently most of the effort is on the code, so this only touches briefly on the high level

# Introduction

## Evolution of the Internet

The Internet and World Wide Web provide a global utility for humanity. They are a set of interrelated protocols and services. The vision of such a network, an Intergalactic network, was first formulated by [Licklider](https://en.wikipedia.org/wiki/J._C._R._Licklider) in the early 1960’s (see [Man-Computer Symbiosis](https://en.wikipedia.org/wiki/Man-Computer_Symbiosis)). It was “imagined as an electronic commons open to all, the main and essential medium of informational interaction for governments, institutions, corporations, and individuals.”

With the development of TCP/IP and the infrastructure behind it this became a reality. The Internet protocols define how computers communicate information. The computers at each endpoint of a communication stream need to run programs (network stack) so the data stream between them can be interpreted (through the packet network). Any application on top of this base layer defines specific interactions of the programs: websites, search engines, social networks, all exist in the cyberspace defined by documents and links viewable by the browser and on mobile smartphones.

## Global Transaction system

The Web and Internet was not designed as a transaction system. With the invention of Bitcoin and a native Network currency global transactions become seemless. The question is how much of this can provide a basis for all economic activity. 

A global transaction system (GTXS) is one where users can exchange value and perform economic transactions. These transactions can be any of the following types and essentially cover any economic activity: cash transfer, asset transfer, asset pricing, auction systems, votes, delegation of trust, identification, disputes, contracts, and so on. The technology basis is a distributed ledger system shared by all - a public network which provides storage and transaction validation.

## Communication Protocols

The Internet protocols are defined in standards, among them Request for Comments (RFC’s). The most important ones are RFC 793 - Transmission Control Protocol, RFC 2616 - Hypertext Transfer Protocol, RFC 1035 - Domain names, RFC 5321 - Simple Mail Transfer Protocol. The information flowing between the nodes are communication data which then get interpreted. 

## Transaction Protocols

The fundamental basis of blockchain is that global transaction systems can be built on top of communication systems. Polygon approaches therefore the 
problem on the communications layer first. Communications are distinct messages.

# Architecture

## State and accounts

Polygon is based on an accounts based ledger.

The movement of value is formally defined by transactions. Traditionally extensbility of blockchains were designed through programmable transactions starting with Bitcoin. The sender and receiver of Bitcoins are public keys and the script language defines the possible transactions between these endpoints. The transactions are type-less in that the code is defined in byte code expressions. Ethereum contracts can be much more complex, but similarly are byte code. In the case of Ethereum there are two distinct transactions: Ether and contracts. What a contract does can not be seen unless one understands the higher level code which was compiled into the byte code. 

In Polygon transactions come in various distinct forms i.e. types of transactions (in principle accounts could have types too, that is open for research)

account => transactionTypeSimple => account

account => transactionTypeComplex => account

This means we can contruct the system through iterations of complexity. The first iteration has only simple transaction types i.e. sending and receiving electronic cash.

## Netio layer - Protocols and messaging

Nodes communicate on top of TCP. TCP is a stream orientated protocol. Any application needs to therefore define when and how endpoints consider a stream a succient bit of information i.e. a message. 

"Netio" is the layer for a messaging stack. It is a set of channels and messages routing through these channels. Any interaction between nodes will be encoded in these messages which follow special patterns. This allows to encode any network specific paramters, such as timeouts, liveness, priorities, routing pattterns

## Dapps versus Webapps

technical implementation of generalised dapps
https://github.com/polygonledger/node/blob/master/handlers_app.go

## Identity of delegates

traditonally cryptonetworks use IP addresses for anonymity. We assume that delegates are public entities that at least can create a domain in their region. there using DNS has advantages. any node can use subdomain polygon.examplenode.us which points to IP of the node. if IP address changes, need to change the pointer in DNS. the top level domain has to be a [Country code top-level domain](https://en.wikipedia.org/wiki/Country_code_top-level_domain).

## Immutable data structures

Clojure is an example of a language that has immutable data structures by default. Changes are denoted separately and 
can be coordinated. This is especially useful in the context of distributed systems.

# Economic model

## Governance and changes

The economic model should be abstract such that all stakeholders, community members, developers can share a high level understanding. It can be assumed that the economic model has two major components: rules that are immutable
(like Bitcoin's money supply) and rules that are subject to change. Since the current work is mostly on the 
implementation level we focus on principles and values rather the rules. If the network grows to a more significant size and meaningful activity takes places the role of the network is to implement the consensus of the group.

## Resarch

Proposal for Proof-of-Asset, rough outline [Proof-of-asset](http://enet.io/blockchain/2019/05/25/poa.html)

## References

* https://en.wikipedia.org/wiki/Actor_model
* https://en.wikipedia.org/wiki/Communicating_sequential_processes
* https://clojure.org/about/state
* https://arxiv.org/pdf/1508.05545.pdf Decoupling conflicts for configurable resolution in an open * replication system
* https://interledger.org/interledger.pdf
