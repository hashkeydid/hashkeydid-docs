# Registry

#### Mint DID

The format for a DID name requires a length between 5 and 54 characters, and only allows the use of lowercase letters a-z and digits 0-9.

```solidity
function mint(address to, string memory did) public;
```

* to: DID address
* did: DID name

#### Add authorization address

Authorize a DID to an address so that the address can view your DID information or log in to other systems on your behalf.

```solidity
function addAuth(uint256 tokenId, address addr) public;
```

* tokenId: DID token id
* addr: authorization address

#### Remove authorization address

Remove the address that you had previously authorized.

```solidity
function removeAuth(uint256 tokenId, address addr) public;
```

* tokenId: DID token id
* addr: authorization address
