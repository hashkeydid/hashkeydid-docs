# BasicInfo

#### Check DID Name

Check if DID name is claimed or not.

```solidity
function didClaimed(string memory did) public view returns (bool);
```

* did: DID name

Verify DID format DID name format require length between 5-54, only allow numbers between 0-9 and alphabet between a-z.

```solidity
function verifyDIDFormat(string memory did) public pure returns (bool);
```

* did: DID name

#### Check address

Check if address is claimed or not.

```solidity
function addrClaimed(address addr) public view returns(bool);
```

* addr: user address

#### Get DID

Get DID name by token id.

```solidity
function tokenId2Did(uint256 tokenId) public view returns (string memory);
```

* tokenId: token id

#### Get DID tokenId

Get token id by DID name.

```solidity
function did2TokenId(string memory did) public view returns (uint256);
```

* did: DID name

#### Get issuer address

Get issuer address by DeedGrain contract address.

```solidity
function deedGrainAddrToIssur(address dgAddr) public view returns(address);
```

* dgAddr: DeedGrain contract address

#### Get all authorization addresses

Get all authorization addresses for specific DID.

```solidity
function getAuthorizedAddrs(uint256 tokenId) public view returns (address[] memory);
```

* tokenId: DID token id

#### Check if address authorized

Check if the address is authorized or not.

```solidity
function isAddrAuthorized(uint256 tokenId, address addr) public view returns (bool);
```

* tokenId: DID token id
* addr: authorization address
