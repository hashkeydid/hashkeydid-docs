# KYC

#### Add KYC

Add KYC information obtained from a KYC provider.

```solidity
function addKYC(uint256 tokenId, address KYCProvider, uint256 KYCId, bool status, uint256 updateTime, uint256 expireTime, bytes memory evidence);
```

* tokenId: DID token id
* KYCProvider: KYC provider address
* KYCId: KYC level
* status: is KYCed or not
* updateTime: update time
* expireTime: expire time
* evidence: signature provided by KYCProvider

#### Get KYC Information

Retrieve the KYC information for a specific DID.

```solidity
function getKYCInfo(uint256 tokenId, address KYCProvider, uint256 KYCId);
```

* tokenId: DID token id
* KYCProvider: KYC provider address(you can find the [provider list](../kyc.md#kyc-providers))
* KYCId: KYC level
