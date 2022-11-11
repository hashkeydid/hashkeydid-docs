# Register Guide

## Sequence Diagram

```mermaid
sequenceDiagram
    actor User
    participant Your App
    participant Hashkey DID
    User->>Your App: Register
    Your App->>+Hashkey DID: checkDIDExistOnChain
    Hashkey DID-->>-Your App: Not exist
    Your App->>+Hashkey DID: registerAndClaim
    Hashkey DID-->>-Your App: Claim successful
	Your App->>User: Register success 
```

## Step by step

### Preparation

For DID registration, user need provide information below:

 - DID: A string as user's DID, suffix is .key, only can contains lower alphabets and numbers, at least, at least 5 characters.
 - Username: A string as user's Display Name, only can contains alphabets, at least 1 character and maximum is 50 characters.
 - Avatar Parts: User could select a head, a body and a footer to create their owner avatar,
	 - head_photos: https://static.hashkey.id/resources/images/fireworks/cartoon/header_{number}.png (i.e. https://static.hashkey.id/resources/images/fireworks/cartoon/header_1.png), 1 to 40.
	 - body_photos: https://static.hashkey.id/resources/images/fireworks/cartoon/body_{number}.png (i.e. https://static.hashkey.id/resources/images/fireworks/cartoon/body_1.png) 1 to 40.
	 - footer_photos: https://static.hashkey.id/resources/images/fireworks/cartoon/footer_{number}.png (i.e. https://static.hashkey.id/resources/images/fireworks/cartoon/footer_1.png) 1 to 40
 - Background Color: https://static.hashkey-qa.id/resources/images/app/card/selection/{number}.svg (i.e. https://static.hashkey-qa.id/resources/images/app/card/selection/1.svg) 1 to 8
	 
### Check DID Exist

Invoke [Check DID Exist API](../api-reference/openapi#get-user-didexistchain) to check if DID exist on chain.

### Register and Claim DID

Invoke [Get Register Claim Sign Text](../api-reference/openapi#get-user-getregisterclaimsigntext) to get sign text.

Let user do personal_sign to whole signText

And using sign result and signId to invoke [Register And Claim](../api-reference/openapi#post-user-registerandclaim) to register and claim a DID .

