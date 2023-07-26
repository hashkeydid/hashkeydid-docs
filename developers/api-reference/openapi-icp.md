# HashKey DID OpenAPI For Dfinity

> Version 1.0

HashKey DID API for dfinity

## Path Details

- API Endpoint: https://api.hashkey.id/icp/api


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
	// Principal for user
    principal?: string
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
  principal?: string
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
}
```
