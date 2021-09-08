### Hi there 👋

<!--
**Dustone25/Dustone25** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

API
API documentation
API documentation
Introduction
General stats endpoints
Retrieve overall information about blockchains and tokens
Dashboard endpoints
Retrieve information about various entities in a neat format from our databases
Raw data endpoints
Retrieve raw information about various entities directly from our full nodes
Infinitable endpoints
SQL-like queries: filter, sort, and aggregate blockchain data
Misc endpoints
Privacy-o-meter
News aggregator
Support
Show all
Blockchair API
Blockchair API
Blockchair API provides developers, researchers, and businesses with access to data contained in 17 blockchains
Explore pricing plans
Blockchair.com API v.2.0.80 Documentation
    ____  __           __        __          _     
   / __ )/ /___  _____/ /_______/ /_  ____ _(_)____
  / __  / / __ \/ ___/ //_/ ___/ __ \/ __ `/ / ___/
 / /_/ / / /_/ / /__/ ,< / /__/ / / / /_/ / / /    
/_____/_/\____/\___/_/|_|\___/_/ /_/\__,_/_/_/     
                                                   
Introduction
Blockchair API provides developers with access to data contained in 18 different blockchains. Unlike other APIs, Blockchair also supports numerous analytical queries like filtering, sorting, and aggregating blockchain data.

Here are some examples of what you can build using our API:

A wallet supporting multiple blockchains (request transaction, address, xpub data, and also broadcast transactions)
An analytical service showing some blockchain stats and visualizations
A service tracking the integrity of your or your customers' cold wallets
A solid academic research
Some fun stuff like finding the first Bitcoin block over 1 megabyte in size
For some tasks like extracting lots of blockchain data (e.g. all transactions over a 2 month period) it's better to use our Database dumps feature instead (see https://blockchair.com/dumps for documentation) — it's possible to download the entire database dumps in TSV format and insert the data onto your own database server (like Postgresql or whatever) to further analyze it.

Almost every API endpoint description is accompanied with an example visualization of the data on our website (https://blockchair.com), and it's also worth it to note that the website is working completely using our API (yes, even the data for charts is pulled from one of our endpoints, and it's fully customizable).

Blockchair cares about user privacy, we neither collect nor share with anyone your personal data rather than for statistical purposes. That includes using the API as well. Please refer to our Privacy policy: https://blockchair.com/privacy. Please also check out our Terms of service available here: https://blockchair.com/terms — by using our API, you are agreeing to these terms.

We have a public tracker for bugs, issues, and questions available on GitHub: https://github.com/Blockchair/Blockchair.Support/issues — please use it or contact us by any other means available.

Our API is free to try under some limitations, and we have a variety of premium plans. Please check out the information about the limits and plans.

Supported blockchains and second layers
As of today, our API supports 19 blockchains (17 mainnets and 2 testnets) divided into 9 groups:

Bitcoin-like blockchains (Bitcoin, Bitcoin Cash, Litecoin, Bitcoin SV, Dogecoin, Dash, Groestlcoin, Zcash, eCash, Bitcoin Testnet), also known as UTXO-based blockchains
Ethereum-like blockchains (Ethereum, Ethereum Goerli Testnet)
Ripple-like blockchains (Ripple)
Stellar-like blockchains (Stellar)
Monero-like blockchains (Monero)
Cardano-like blockchains (Cardano)
Mixin-like DAGs (Mixin) — technically, it's a DAG rather than a blockchain, but for the sake of unification it may be mentioned as a blockchain further in this documentation
Tezos-like blockchains (Tezos)
EOS-like blockchains (EOS)
Within a group, there's no or little difference between the set of available endpoints and their output.

Here's the list of available mainnets:

Blokchain	Group	API path prefix	Support status
Bitcoin	Bitcoin-like	https://api.blockchair.com/bitcoin	Full support
Bitcoin Cash	Bitcoin-like	https://api.blockchair.com/bitcoin-cash	Full support
Ethereum	Ethereum-like	https://api.blockchair.com/ethereum	Full support
Litecoin	Bitcoin-like	https://api.blockchair.com/litecoin	Full support
Bitcoin SV	Bitcoin-like	https://api.blockchair.com/bitcoin-sv	Full support
Dogecoin	Bitcoin-like	https://api.blockchair.com/dogecoin	Full support
Dash	Bitcoin-like	https://api.blockchair.com/dash	Full support
Ripple	Ripple-like	https://api.blockchair.com/ripple	Alpha mode, possible compatibility-breaking changes
Groestlcoin	Bitcoin-like	https://api.blockchair.com/groestlcoin	Full support at least till January 1st, 2021
Stellar	Stellar-like	https://api.blockchair.com/stellar	Alpha mode, possible compatibility-breaking changes
Monero	Monero-like	https://api.blockchair.com/monero	Alpha mode, possible compatibility-breaking changes
Cardano	Cardano-like	https://api.blockchair.com/cardano	Alpha mode, possible compatibility-breaking changes
Zcash	Bitcoin-like	https://api.blockchair.com/zcash	Full support
Mixin	Mixin-like	https://api.blockchair.com/mixin	Full support at least till April 24th, 2021
Tezos	Tezos-like	https://api.blockchair.com/tezos	Alpha mode, possible compatibility-breaking changes
EOS	EOS-like	https://api.blockchair.com/eos	Alpha mode, possible compatibility-breaking changes
eCash	Bitcoin-like	https://api.blockchair.com/ecash	Beta mode, possible instability. Also known as Bitcoin Cash ABC and Bitcoin ABC.
Please read our statement on the November 15th, 2020 Bitcoin Cash split: https://twitter.com/Blockchair/status/1324424632179576832. It is expected that Bitcoin ABC's hashrate will be very low so 51% attacks are possible. We'll be running Bitcoin ABC in beta mode and we don't guarantee neither its stability, nor that we'll run it if the chain won't be used by businesses. Once the situation becomes more stable we'll update the documentation. At the moment, other parts of the documentation don't reflect Bitcoin ABC support, so please assume that for every bitcoin-cash endpoint there's a bitcoin-abc equivalent except for https://api.blockchair.com/bitcoin-cash/nodes.

There are also following testnets supported which are technically considered as separate blockchains:

Blokchain	Group	API path prefix	Support status
Bitcoin Testnet	Bitcoin-like	https://api.blockchair.com/bitcoin/testnet	Full support
Ethereum Goerli Testnet	Ethereum-like	https://api.blockchair.com/ethereum/testnet	Development mode, no guaranteed stability
