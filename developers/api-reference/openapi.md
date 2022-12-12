# HashKey DID OpenAPI

> Version 1.0

HashKey DID API for public

## Path Details

- API Endpoint: https://api.hashkey.id/did/api

### [POST]/user/didExist

- Summary  
User DID Exists

- Description  
Check if user already has a HashKey DID

#### RequestBody

- application/json

```ts
{
  // 0x address
  addr: string
}
```

- application/xml

```ts
{
  addr?: string
}
```

#### Responses

- 200 User Created

`application/json`

```ts
{
  // 200 is success
  code?: integer
  data: {
    // User DID status, "1" is normal.
    status?: string
    // true is existed
    exitFlag?: boolean
    // User'guides DID when existed.
    did?: string
  }
  msg?: string
}
```

- Examples

  - example-1

```json
{
  "value": {
    "code": 0,
    "data": {
      "status": "string",
      "exitFlag": true,
      "did": "string"
    },
    "msg": "string"
  }
}
```

- 400 Missing Required Information

- 409 Email Already Taken

-  undefined

`application/json`

```ts
{
}
```

***

### [GET]/user/didExistChain

- Summary  
DID exist on chain

- Description  
Check if a DID already has been taken

#### Parameters(Query)

```ts
did?: string
```

#### Responses

- 200 OK

`application/json`

```ts
{
  // 200 is success
  code?: integer
  // true when DID existed on chain
  data?: boolean
  msg?: string
}
```

***

### [POST]/user/registerAndClaim

- Summary  
Register and Claim DID

- Description  
Register a user, and we will airdrop a DID to user on PlatON.

#### RequestBody

- application/json

```ts
{
  // 0x address
  addr?: string
  // User'guides DID, only can contains a-z, 0-9, at least 5 characters.
  did?: string
  // User'guides nickname
  nickname?: string
  // 1-8, other value will be the default background, same as 1
  backgroundNumber?: integer
  // "h1,b1,f1" is the format, number could in range 1-40
  photoParts?: string
  // Using personal_sign to sign "signText" from "get register claim sign text" API.
  sign?: string
  // Get it from "get register claim sign text" API.
  signId?: string
  // Wallet name, when this document is written, "kaikas" is the only reasonable value need to fill.
  wallet?: string
}
```

#### Responses

- 200 OK

`application/json`

```ts
{
  code?: integer
  data: {
    // Transaction Hash for airdrop transaction.
    txHash?: string
  }
  msg?: string
}
```

***

### [GET]/chain/{chainName}/transaction/{txHash}

- Summary  
Transaction Details

- Description  
Get transaction details.

#### Responses

- 200 OK

`application/json`

```ts
{
  code?: integer
  data: {
    hash?: string
    nonce?: integer
    type?: integer
    to?: string
    value?: string
    gas?: integer
    gasPrice?: string
    data?: string
    // transaction pending status.
    pending?: boolean
    // 0 as success and 1 as fail
    status?: integer
  }
  msg?: string
}
```

***

### [GET]/user/getRegisterClaimSignText

- Summary  
Get Sign Text for Register And Claim

- Description  
Get Sign Text for Register And Claim

#### Parameters(Query)

```ts
addr?: string
```

#### Responses

- 200 OK

`application/json`

```ts
{
  code?: integer
  data: {
    // Text for personal_sign
    signText?: string
    // signId should fill in register and claim API
    signId?: string
  }
  msg?: string
}
```

***

### [GET]/did/{did}

- Summary  
Get DID info

- Description  
Get DID info

#### Responses

- 200 OK

`application/json`

```ts
{
  code?: integer
  data: {
    id?: integer
	// DID for user
    did?: string
	// Address for user
    addr?: string
	// Token ID for user in DID nft contract
    tokenId?: string
    userInfo: {
      userId?: integer
	  // Nickname for user
      nickname?: string
	  // DID card url for user. Full url with protocol and host.
      photoUrl?: string
	  // User card background number
      backgroundNumber?: integer
	  // User card backfrount number
      backfrontNumber?: integer
	  // Avatar url for user. Full url with protocol and host.
      headUrl?: string
      photoParts?: string
    }
	// User following count
    followingTotal?: integer
	// User follower count
    followerTotal?: integer
	// Time for DID claimed at
    claimAt?: string
  }
  msg?: string
}
```

### [GET]/deedgrain/collected/credential/{did}

- Summary  
List OSTs for did

#### Responses

- 200 OK

`application/json`


```ts
{
  code?: integer
  data: {
    id?: integer
    userId?: integer
    // OST name
    name?: string
    assetType?: integer
    assetValue?: integer
    // OST index
    idIndex?: integer
    // OST Contract Address
    contactAddr?: string
    // OST Owner Address
    ownerAddr?: string
    // OST Token ID
    tokenId?: string
    // OST Metadata
    nftData?: string
    // OST Mint transaction hash 
    txHash?: string
	// Image URL for OST. Full URL with protocol and host
    imageUrl?: string
	// External URL for OST if exists in metadata. Full URL with protocol and host
    externalUrl?: string
	// Animation URL for OST if exists in metadata. Full URL with protocol and host
    animationUrl?: string
	// Chain Name, any of ["Ethereum", "PlatON", "Klaytn"]
    chainName?: string
    deedgrainActivityId?: integer
    createdAt?: string
    updatedAt?: string
	// Activity Key, if you want give user a mint link, you could use this key in url. Format is https://www.hashkey.id/credential/{activityKey}
    activityKey?: string
  }[]
  msg?: string
}
```


### [GET]/deedgrain/collected/nft/{did}

- Summary  
List User NFTs

#### Parameters(Query)

```ts
pageNum?: integer
```

```ts
pageSize?: integer
```

#### Responses

- 200 OK

`application/json`

```ts
{
  code?: integer
  data: {
    code?: integer
    error_code?: string
    msg?: string
    data: {
      pageNum?: integer
      pageSize?: integer
      total?: integer
      list: {
        id?: integer
        ownerAddr?: string
        contractAddress?: string
        tokenId?: string
        tokenUrl?: string
        image?: string
        imageData?: string
        externalUrl?: string
        description?: string
        name?: string
        attributes?: string
        backgroundColor?: string
        animationUrl?: string
        youtubeUrl?: string
        imageUrl?: string
        floor?: string
        contractName?: string
        chainName?: string
        lastTransferTime?: string
        createdAt?: string
        updatedAt?: string
      }[]
    }
  }
  msg?: string
}
```

## References

### #/components/schemas/DIDInfo

```ts
{
  id?: integer
  did?: string
  addr?: string
  tokenId?: string
  userInfo: {
    userId?: integer
    nickname?: string
    photoUrl?: string
    backgroundNumber?: integer
    backfrontNumber?: integer
    headUrl?: string
    photoParts?: string
    createdAt?: string
    updatedAt?: string
    ldz?: string
  }
  createdAt?: string
  updatedAt?: string
  status?: string
  loginToken?: string
  followingTotal?: integer
  followerTotal?: integer
  claimAt?: string
  chainName?: string
}
```

### #/components/schemas/OST

```ts
{
  id?: integer
  userId?: integer
  name?: string
  assetType?: integer
  assetValue?: integer
  idIndex?: integer
  contactAddr?: string
  ownerAddr?: string
  tokenId?: string
  nftData?: string
  txHash?: string
  imageUrl?: string
  externalUrl?: string
  animationUrl?: string
  chainName?: string
  deedgrainActivityId?: integer
  createdAt?: string
  updatedAt?: string
  activityKey?: string
}
```

### #/components/schemas/NFT

```ts
{
  id?: integer
  ownerAddr?: string
  contractAddress?: string
  tokenId?: string
  tokenUrl?: string
  image?: string
  imageData?: string
  externalUrl?: string
  description?: string
  name?: string
  attributes?: string
  backgroundColor?: string
  animationUrl?: string
  youtubeUrl?: string
  imageUrl?: string
  floor?: string
  contractName?: string
  chainName?: string
  lastTransferTime?: string
  createdAt?: string
  updatedAt?: string
}
```
