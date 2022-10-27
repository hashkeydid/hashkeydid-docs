# KYC

### Introduce

KYC means Know Your Customer and sometimes Know Your Client. KYC or KYC check is the useful process of identifying and verifying the client's identity when opening an account and periodically over time. Country to the traditional business industry, KYC certification is optional in HashKey DID.

### Architecture

<figure><img src="../.gitbook/assets/kyc.png" alt=""><figcaption></figcaption></figure>

### How to add KYC

If DID user want to add KYC, you need to contact KYC provider and send the required parameters to KYC provider. KYC provider will sign the parameters with private key. User call the DID contract to add KYC with signature from KYC provider. For more details, please visit Add KYC.
