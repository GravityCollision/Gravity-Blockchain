# Gravity-Blockchain
Our Respository for the Gravity Blockchain, it's Streamchain and Nodes.

# The Blockchain

The Gravity Blockchain sits on top of Ethereum.  It's main purpose, is to ensure the quick creation of Assets, that will be used in Games.  Becuase of the requirements of Videogames, and their In Game Items, we would require around 50,000 Assets generated per second.  These Assets can be any number of In-Game Items.  Whatever they represent, they need to be made fast, and delivered to the Game Studio that requested it.

The Foundation of our Blockchain, is in it's Decentralization.  When someone Plays our Games, they have the option to use a small portion of their Compute Power, to join the Blockchain.  Our Blockchain uses a Role-Based Node approach, that keeps everything in check.  There are many Node Types.  These Nodes process Fulfillment Requests, that Game Studios make.  These Nodes are segregated from each other, in Streamchains.  They communicate and process, only when they are required to.  Depending on the status of a particular Asset on our Blockchain, it may or may not be tracked by particular Nodes.  This type of Blockchain is assymetrical by design.  The Streams and associated Nodes below, is the minimum design needed to achieve 50,000 Transactions / Second.

Director Stream

     • Comprised of Director Nodes
     • These maintain a route lookup table of nearby Nodes in different streamchains
     • Processes and provides Routing Data for a ‘CALL’ (FR)

Minter Stream

     • Comprised of Minter Nodes
     • Creates an Asset based on parameters given to it
     • Forwards results to a Validator Node(s)

Validator Stream

     • Comprised of Validator Nodes
     • Checks results of Minted Assets, to ensure they meet the parameters given
     • Checks results of Aggregator Node’s Block Consensus
     • Forwards to a Library Node

Library Stream

     • Comprised of Library Nodes
     • Library Nodes are Nodes operated by Company who is using our Blockchain
     • Stores Assets until distributed to a Player
     • Assets in Libraries are considered ‘AT REST’

Archive Stream

     • Comprised of Archive Nodes
     • Stores the Full Blockchain on each Node
     • Off-chain Asset records are stored here
     • Assets in the Archives are considered ‘AT REST’

Garbage Stream

     • Comprised of Garbage Nodes
     • Maintains a list of Assets that have been destroyed (melted) or dissolved
     • Purges Garbage at a specified interval
     • Purged Assets are no longer tracked by the Blockchain

Inspector Stream

     • Comprised of Inspector Nodes
     • Audits Libraries Node for consistent behavior
     • Audits Garbage Nodes for consistent behavior
     • Audits Archive Nodes for consistent behavior
     • Investigates ‘INVALID CALLS’
     • Forwards investigation results to an Enforcer Node

Aggregator Stream

     • Comprised of Aggregator Nodes
     • Maintains the portion of the Blockchain that is not ‘AT REST’
     • Compares ‘CALL’ Results (depending on Security Level) and writes to Blockchain

Encryption Stream

     • Comprised of Encryption Nodes
     • Accepts WEB3 Parameter Data from Outside the Network
     • Encrypts & Decrypts Parameter Data to pseudo-random data
     • Processes ‘CALL REPLAY’ Events

Enforcer Stream

     • Comprised of Enforcer Nodes
     • Acts against Malicious Nodes
     • Action depends on severity
     • Initiates ‘CALL REPLAY’ Events
