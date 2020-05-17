# whitepaper

(draft)

## architecture

Polygon is based on an accounts based ledger.

The movement of value is formally defined by transactions. Traditionally extensbility of blockchains were designed through programmable transactions starting with Bitcoin. The sender and receiver of Bitcoins are public keys and the script language defines the possible transactions between these endpoints. The transactions are type-less in that the code is defined in byte code expressions. Ethereum contracts can be much more complex, but similarly are byte code. In the case of Ethereum there are two distinct transactions: Ether and contracts. What a contract does can not be seen unless one understands the higher level code which was compiled into the byte code. 

In Polygon transactions come in various distinct forms i.e. types of transactions (in principle accounts could have types too, that is open for research)

account => transactionTypeSimple => account

account => transactionTypeComplex => account

This means we can contruct the system through iterations of complexity. The first iteration has only simple transaction types i.e. sending and receiving electronic cash.

## protocols and messaging

Nodes communicate on top of TCP. TCP is a stream orientated protocol. Any application needs to therefore define when and how endpoints consider a stream a succient bit of information i.e. a message. 

"Netio" is the layer for a messaging stack. It is a set of channels and messages routing through these channels. Any interaction between nodes will be encoded in these messages which follow special patterns. This allows to encode any network specific paramters, such as timeouts, liveness, priorities, routing pattterns

## identity of delegates

traditonally cryptonetworks use IP addresses for anonymity. We assume that delegates are public entities that at least can create a domain in their region. there using DNS has advantages. any node can use subdomain polygon.examplenode.us which points to IP of the node. if IP address changes, need to change the pointer in DNS. the top level domain has to be a [Country code top-level domain](https://en.wikipedia.org/wiki/Country_code_top-level_domain).