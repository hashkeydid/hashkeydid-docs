# BasicInfo

#### Check DID Name

Check whether a DID name has been claimed or not.

```solidity
function didClaimed(string memory did) public view returns (bool);
```

* did: DID name

#### Verify DID Format

To verify the DID format, ensure that the DID name has a length between 5 and 54 characters, and only contains the characters 0-9 and lowercase letters a-z.

```solidity
function verifyDIDFormat(string memory did) public pure returns (bool);
```

* did: DID name

#### Check address

Check whether an address has been claimed or not.

```solidity
function addrClaimed(address addr) public view returns(bool);
```

* addr: user address

#### Get DID

Retrieve the DID name by token id.

```solidity
function tokenId2Did(uint256 tokenId) public view returns (string memory);
```

* tokenId: token id

#### Get DID tokenId

Retrieve the token id by DID name.

```solidity
function did2TokenId(string memory did) public view returns (uint256);
```

* did: DID name

#### Get issuer address

Retrieve the issuer address by DeedGrain contract address.

```solidity
function deedGrainAddrToIssur(address dgAddr) public view returns(address);
```

* dgAddr: DeedGrain contract address

#### Get all authorization addresses

Retrieve all authorization addresses for specific DID.

```solidity
function getAuthorizedAddrs(uint256 tokenId) public view returns (address[] memory);
```

* tokenId: DID token id

#### Check if address authorized

Check whether a DID has been authorized to the address or not.

```solidity
function isAddrAuthorized(uint256 tokenId, address addr) public view returns (bool);
```

* tokenId: DID token id
* addr: authorization address
