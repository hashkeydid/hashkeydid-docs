# DID as NFT

HashKey DID contract is based on [ERC721](https://eips.ethereum.org/EIPS/eip-721), meaning that .key registrations have their own metadata in their tokenURIs including name, description, image, etc. But the DID can not be transferred so far.

### Metadata

Metadata is a json string which includes the basic data of an NFT.

The metadata can be found by `curl https://api.hashkey.id/did/api/nft/metadata/{tokenId}`.

```json
{
  "name": "chingizyanik.key",
  "description": "Your Passport in the Metaverse",
  "image": "https://api.hashkey.id/did/api/file/avatar_117e6412-ba3f-4acd-a5a3-b171e5acfb17.png",
  "ipfs_url": "https://arweave.net/ySMzJkoSdbM9jWsmm4W6Glsk1HapTluMVG1oyi5QpaA"
}
```

### Display

HashKey DID's main contracts is deployed on [PlatON](https://www.platon.network/), so the DID NFT can be found on the HashKey DID DAPP and platforms that support PlatON such as [tofu](https://tofunft.com/platon).
