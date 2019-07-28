# diafaneos - Transparent, secure voting systems, powered by Azure blockchain

# PROBLEM STATEMENT
Elections, referenda, and polls are very important processes & tools for the smooth operation of a modern democracy.
Build a Proof-of-Concept to demonstrate how you can make these processes more secure, reliable, and transparent using Azure Blockchain.

# DESRIPTION OF REQUIREMENTS

The main issue with implementing blockchains at the levels of millions of nodes are :

* Evading bottlenecks in transaction speed
* Minimising computing power needed
* Ensuring immutability and verifiability of data
* Reducing cost to levels that are comparable or lower than current technology
* Staying secure enough to be accepted as realistically tamper-proof without sacrificing any of the points listed above

Currently, India is the world's largest democracy and as such, any solution should have target capability of being able to conduct an election of 1.2 billion people without compromising on transparency and immutability, or becoming cost-ineffective for these countries.

# DESCRIPTION OF FRAMEWORK/PROTOCOL

Diafenos stems from the greek _diafáneia_ meaning "transparent".

Diafaneos relies on leveraging existing infrastructure and its own sidechains to use the available computing power efficiently while also increasing the number of nodes in the network. 

The network will comprise of a main chain, and one sidechains for each constituency/political subdivision that needs to be monitored.

The sidechain would be responsible for recording every vote that has been registered in its constituency. Since every vote is with a unique hash, we can ensure traceability at the constituency level. The block size for this blockchain is kept small : the emphasis is on getting a high transaction rate, d0sor else the voting process itself will bottleneck.

In essence, the sidechain is saving each vote as it is being cast. A parser keeps a tally of the votes cast in a set interval

The status of this sidechain would be sent to the main blockchain at these set intervals (say, 1 minute) by the parser. These blocks, which would be part of the main blockchain, would have larger block sizes. The main blockchain is saving a (so to say) minute-by-minute update of each constituency's voting pattern.

With this setup consensus is reached by Proof of Authority. The main blockchain is developed only by a designated network of computers, while other nodes can validate it. Therefore, every node acts as a checkpoint against fraud anywhere else, as that will mess up a small nuber of computers. In the case of a national election/referendum, this means a node setup of millions of validators who are checking the work of a few hundred powerful computer node.

# HOW IT WORKS

1. The area to be surveyed is already divided into political constituencies. On the network level, these constituencies are made to comprise of a lot of nodes centered around a validator computer.

2. A computer office building, or the parallelized labs of engineering or scientific research instituions spread across the country can be leased to act as said validators. This provides cheap and repurpose-able hardware for a blockchain supposed to deliver sufficient thoroughput. Azure blockchain technology can then be leveraged on these buildings to augment computing power whilst adding nodes to make the system more robust.

3. Each of these complexes would have their own sidechain that would record individual votes in small sized blocks, therefore allowing for a higher rate of addition to the sidechain. These are partially centralised models, in which we are leasing/commandeering computing resources from software parks and buildings. These buildings act as validators and sync with the main chain. 

4. Local schools or buildings with lots of computers in these constituencies will serve as polling booths. Every voter card would have its unique hash, which would let them stay anonymous on the network. These computers can run Azure supported web clients for casting votes.

5. The votes from these polling booth will be fed into their sidechains. The sidechain keeps getting parsed at regular intervals and then tally for that minute at that constituency is sent via sidechain validator (high-computing power node) to the main chain.

6. The main chain is synced by these validator nodes, so any tampering can be seen immediately. More importantly, any tampering done is rejected instantaneously to keep most of the data alive, thus helping reduce the need for by-elections etc.

7. At the end of the voting process, the parser can be run through the mainchain as a whole to get the results. It can then be verified using copies available at random nodes, as well as with the sidechains.

# NOTES

Please let us know if something can be improved or simplified to make this more practically scalable or robust, or somethign that can be done to
