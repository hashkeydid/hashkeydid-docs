# PublicResolver

### Abstract

The Resolver contract stores the personal information of a DID user, such as their name, avatar, and blockchain addresses. The DID user can choose to store their personal information through the Resolver contract, and all of the information fields are optional.

### Reverse resolution

We are familiar with DNS resolution, which resolves domain names to IP addresses, and reverse resolution, which resolves IP addresses to domain names. Similarly, the reverse resolution of DID allows for the association of human-readable names with blockchain addresses and the resolution of machine-readable identifiers to human-readable identifiers.

#### Get reverse resolution

To use the reverse resolution function, you only need to call the following function in the Resolver contract.

```solidity
function name(address _addr) public view returns (string memory);
```

* addr: get addr's DID name

### Blockchain addresses

Wallet developers are beginning to require the ability to resolve multiple blockchain addresses in the DID, and this specification standardizes the means of entering and retrieving these addresses. Users can set multiple blockchain addresses for DID.

#### Add address

Call the following function to add the address for DID. `coinType` is the cryptocurrency type indexed by [SLIP44](https://github.com/satoshilabs/slips/blob/master/slip-0044.md).

```solidity
function setAddr(uint256 tokenId, uint256 coinType, bytes memory _addr) public authorized(tokenId);
```

* tokenId: DID tokenId
* coinType: the cryptocurrency type indexed by [SLIP44](https://github.com/satoshilabs/slips/blob/master/slip-0044.md)
* \_addr: blockchain address

#### Get address

Access the DID-bound blockchain addresses and call the following function.

```solidity
function addr(uint256 tokenId, uint256 coinType) public view returns(bytes memory);
```

* tokenId: DID tokenId
* coinType: the cryptocurrency type indexed by [SLIP44](https://github.com/satoshilabs/slips/blob/master/slip-0044.md)

### Ecdsa secp256k1 public key

DID users can set the Ecdsa secp256K1 public key. When the user uses the private key to sign information, the receiver can use the public key to verify the signature. When the receiver wants to encrypt the communication with the DID User, the receiver can use the public key to encrypt the communication information, and the DID User uses the private key to decrypt the information.

#### Set public key

In the resolver contract, the following function is called to set the public key.

```solidity
function setPubkey(uint256 tokenId, bytes32 x, bytes32 y) external authorized(tokenId);
```

* tokenId: DID tokenId
* x: the x coordinate of the curve point for the public key
* y: the y coordinate of the curve point for the public key

#### Get public key

Call the following function to query the public key.

```solidity
function pubkey(uint256 tokenId) external view returns (bytes32 x, bytes32 y);
```

* tokenId: DID tokenId

### Text

The user can set some attributes for DID eg: `name`, `age` to store.

#### Set text

The following function is used to set text.

```solidity
function setText(uint256 tokenId, string calldata key, string calldata value) external authorized(tokenId);
```

* tokenId: DID tokenId
* key: eg: `name`
* value: eg: `allen`

Note: The `avatar` field is used when the user wants to set an avatar for himself. The field value URI should follow the following rules:

* HTTP: If you provide an HTTP URI, it should be able to parse directly into an avatar image, rather than a traditional HTML page, metadata, or other content.
* IPFS: If an IPFS URI is provided, it should be able to parse directly into an avatar image. Clients without built-in IPFS support can rewrite the URI as an HTTPS URL referencing the IPFS gateway before parsing. As described in [this document](https://docs.ipfs.io/how-to/address-ipfs-on-web/).
*   NFT: NFT can also be used as the profile picture of DID. When setting the profile picture URI, you need to follow the following standards:

    ```shell
    nft:chainId:tokenType:contractAddress:tokenId
    ```

    * nft: protocol name
    * chainId: chain ID
    * tokenType: token type, eg: `721/1155`
    * contractAddress: contract address
    * tokenId: NFT's tokenId

#### Get text

The following function is used to query the text.

```solidity
function text(uint256 tokenId, string calldata key) external view returns (string memory);
```

* tokenId: DID tokenId
* key: eg: `name`
