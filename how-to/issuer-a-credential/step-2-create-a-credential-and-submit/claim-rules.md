# Claim rules

There are three types of rules you can use:&#x20;

* [Own a Hashket DID](claim-rules.md#1.-own-a-hashkey-did)
* [White list](claim-rules.md#2.-white-list)
* [Custom API](claim-rules.md#3.-custom-api)

You can choose any one, two or all of them. We will explain each rule below.



## 1. Own a HashKey DID

_For each credential, this rule can only be used once._ \
This rule means only users with a HashKey DID are eligible to claim the credential.

![](<../../../.gitbook/assets/image (6).png>)



## 2. White list

_For each credential, this rule can only be used once._\
__This rule means only users in the whitelist are able to claim the credential. The whitelist can only be set after adding this rule.

![](<../../../.gitbook/assets/image (12).png>)

**Rule description:** \
****This is a required field. A specific description of this rule will be displayed to the users.

**Event URL:** \
****This is an optional field. If you have an additional link for this rule, please add them here.

If any White list rule is added, The whitelist can be added after the credential is created.\
For how to add a whitelist, please refer to '[Manage your credential](../../manage-your-credential.md)'.



## 3. Custom API

_For each credential, this rule can be used multiple times._\
__This rule means only users who meet the API requirements are able to claim the credential.

![](<../../../.gitbook/assets/image (1).png>)

**Rule description:** \
****This is a required field. A specific description of this rule will be displayed to the users.

**Event URL:** \
****This is an optional field. If you have an additional link for this rule, please add them here.

**API Endpoint:**\
****This is a required field. You need to enter a full API URL. For API writing methods, please refer to '[Credential API Rule](../../../developers/guides/credential-api-rule.md)' for details.

**API Test Module:** \
****In the Custom API rules, we also provide the API Test Module. You could enter an address to test whether this API is usable. We currently only support addresses starting with 0x.

****
