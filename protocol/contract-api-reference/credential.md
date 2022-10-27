# Credential

#### Set Transferable

Credential could be transferable or non-transferable. The function can reverse it. Can only be invoked by issuer or HashKey did.

```solidity
function reverseTransferable() public onlyControllers;
```

#### Set Supply

Credential could be fixed supply. Credential is [ERC-1155](https://eips.ethereum.org/EIPS/eip-1155) token.Can only be invoked by issuer or HashKey did.

```solidity
function setSupply(uint256 tokenId, uint256 supply) public onlyControllers;
```

* tokenId: DID token id
* supply: max supply

#### Set BaseURI

Set token BaseURI. Can only be invoked by issuer.

```solidity
function setBaseUri(string memory baseUri) public;
```

* baseUri: [ERC-1155](https://eips.ethereum.org/EIPS/eip-1155) base URI

#### Get URI

return BaseURI/tokenID. For example:\
if: BaseURI = https://api.hashkey-qa.id/did/api/nft/metadata/ && tokenId = 1\
then: URI = https://api.hashkey-qa.id/did/api/nft/metadata/1

```solidity
function uri(uint256 tokenId) public view override returns (string memory);
```

* tokenId: DID token id

#### Issue DeedGrain

Institution get evidence signed by HashKey DID. Use the evidence to issue DeedGrain.

```solidity
function issueDG (string memory _name, string memory _symbol, string memory _baseUri, bytes memory _evidence, bool _transferable) public;
```

* \_name: ERC1155 NFT name
* \_symbol: ERC1155 NFT symbol
* \_baseUri: ERC1155 NFT baseUri
* \_evidence: signature by HashKey DID
* \_transferable: whether DeedGrain is transferable
