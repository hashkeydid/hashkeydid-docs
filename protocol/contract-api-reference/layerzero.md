# LayerZero

#### Sync

Synchronize DID information to the destination chain through LayerZero protocol, including DID, avatar, and KYC information.

```
struct Payload {
    uint256 tokenId;        // did tokenid
    address user;           // did owner
    string did;             // did name
    string avatar;          // avatar url
    address[] KYCProvider;  // kyc provider address
    uint256[] KYCId;        // kyc id (kyc level)
    IDid.KYCInfo[] KYCInfo; // kyc info
    bytes[] evidence;       // kyc evidence signed by provider
    bytes evidenceLZ;       // evidence signed by HashKey DID
}
function sync(Payload memory _payload, uint16 _dstChainId) public;
```

* \_payload: DID infomation
* \_dstChainId: destination chain id defined by [LayerZero](https://layerzero.gitbook.io/docs/technical-reference/mainnet/supported-chain-ids)

#### Mint DID LayerZero

Minting a DID using information obtained from a sync event can only be invoked by the LayerZero endpoint or the HashKey DID endpoint (when the chain is not yet supported by LayerZero).

```
function mintDidLZ(uint256 tokenId, address user, string memory did, string memory avatar, address[] memory KYCProvider, uint256[] memory KYCId, KYCInfo[] memory kycInfo, bytes[] memory evidence)
```

* did infos args: Refer to the annotations of type `Payload` below.
