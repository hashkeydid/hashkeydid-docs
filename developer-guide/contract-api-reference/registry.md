# Registry

#### Mint DID

DID name format require length between 5-54, only allow numbers between 0-9 and alphabet between a-z.

```solidity
function mint(address to, string memory did) public;
```

* to: DID address
* did: DID name

#### Add authorization address

Authorize DID to the address so that the address can view DID information or log in other system on behalf of you.

```solidity
function addAuth(uint256 tokenId, address addr) public;
```

* tokenId: DID token id
* addr: authorization address

#### Remove authorization address

Remove address that you authorized before.

```solidity
function removeAuth(uint256 tokenId, address addr) public;
```

* tokenId: DID token id
* addr: authorization address
