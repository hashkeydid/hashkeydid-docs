# KYC

KYC means Know Your Customer. KYC is the mandatory process of identifying and verifying the client's identity when opening an account and periodically over time.

#### Add KYC

Add KYC information from KYC provider.

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

Get KYC information for specific DID.

```solidity
function getKYCInfo(uint256 tokenId, address KYCProvider, uint256 KYCId);
```

* tokenId: DID token id
* KYCProvider: KYC provider address
* KYCId: KYC level
