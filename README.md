# Introduction

HashKey DID is a decentralized identity project in web3.0. It is an NFT based decentralized identity with features of decentralized storage and privacy. HashKey DID has lived on multiple blockchain, like Ethereum, PlatON, Klaytn, Polygon etc.

The system provides some basic functions: **Registration, Authorization, KYC Service and Credential Issuance**.

#### Registration

The DID name ends with .key suffix and DID avatar can be customized. DID length is between 5 and 54 words, it only allow numbers between 0-9 and alphabet between a-z. Once user has registered, the address and user name will be store in smart contract.

#### Authorization

User can use HashKey DID as his identity to log in other system as long as he authorizes his identity to it.

#### KYC Service

There are some reputable brands cooperating with HashKey DID, user can get KYC from them. And then add KYC information to DID.

#### Issue Credentials

Credential records the unique on-chain footprints of individuals, "freezes" user's on-chain highlights and records active on-chain engagements and achievements. Institution can issue credentials to its user as an ecosystem incentives to reward active and outstanding community contributors and enhance user loyalty.

### HashKey DID Architecture

&#x20;The above is HashKey DID smart contract architecture. The smart contract collect these information:

* The owner of this name
* Credentials related to that address
* KYC information
* Credentials Issuer

HashKey DID protocol consist two different parts. One is DID smart contract, an ERC721 contract. DID contract include four major functionality: **Registration, Authorization, KYC Service and Credential Issuance**. Institution issue credentials for its user, DID contract would create a new contract called DeedGrain. It's an ERC1155 token. Issuer can choose how to motivate user either through fungible token or non-fungible token.

### Getting Started

For DAPP developers and contract developers, HashKey DID document provide comprehensive guidance.

**I'm contract developer and I want to interact with HashKey DID**\
Check out the Contract Developer Guide, starting with [ContractAPI](developer-guide/contract-api-reference/)

**I'm DAPP developer and I want HashKey DID support to my DAPP**\
Check out the DAPP Developer Guide, starting with [Developer](developer-guide)
