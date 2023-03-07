# Credential

#### Set Transferable

Credential could be transferable or non-transferable. The function can reverse it. Can only be invoked by issuer or HashKey DID.

```solidity
function reverseTransferable() public onlyControllers;
```

#### Set Supply

The supply of a credential can be fixed. Can only be invoked by issuer or HashKey DID.

```solidity
function setSupply(uint256 tokenId, uint256 supply) public onlyControllers;
```

* tokenId: DID token id
* supply: max supply

#### Get URI

Retrieve the tokenURI (i.e., the link to the metadata) associated with a given tokenId.

```solidity
function uri(uint256 tokenId) public view override returns (string memory);
```

* tokenId: DID token id

#### Issue DeedGrain

An institution can obtain evidence signed by a HashKey DID and use that evidence to issue DeedGrain.

```solidity
function issueDG (string memory _name, string memory _symbol, string memory _baseUri, bytes memory _evidence, bool _transferable) public;
```

* \_name: credential name
* \_symbol: credential symbol
* \_baseUri: credential baseUri
* \_evidence: signature signed by HashKey DID
* \_transferable: whether DeedGrain is transferable
