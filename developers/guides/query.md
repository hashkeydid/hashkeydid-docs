# Query

Query tokenId's all authorized addrs

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetAuthorizedAddrs} from "hashkeydid-js"
// tokenId: 1222
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryAuthorizedAddrs(){
    let addrs = await GetAuthorizedAddrs(1222, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's KYC information

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetKYCInfo} from "hashkeydid-js"
// tokenId: 1222
// KYCProvider: 0xdeDBB6048b0B9107a21d81E345afe0789229Dbac
// KYCId: 1
// overrides: {"blockTag": 16513266} (search from block number 16513266)
async function QueryKYCInfo(){
    let info = await GetKYCInfo(1222, "0xdeDBB6048b0B9107a21d81E345afe0789229Dbac", 1, {"blockTag": 16513266})
}

```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's DID

{% tabs %}
{% tab title="JS" %}
```javascript
import {TokenId2Did} from "hashkeydid-js"
// tokenId: 1222
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryTokenIdByDid(){
    let did = await TokenId2Did(1222, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query DID's tokenID

{% tabs %}
{% tab title="JS" %}
```javascript
import {Did2TokenId} from "hashkeydid-js"
// did name: terro.key
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryDidByTokenId(){
    let tokenId = await Did2TokenId("terro.key", {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query deedgrain contract issuer

{% tabs %}
{% tab title="JS" %}
```javascript
import {DeedGrainAddrToIssur} from "hashkeydid-js"
// DeedGrain contract address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryDeedGrainIssur(){
    let did = await DeedGrainAddrToIssur("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {"blockTag": 16513266})
}

```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query DID's name by address

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetDIDNameByAddr} from "hashkeydid-js"
// DID address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryDIDNameByAddr(){
    let did = await GetDIDNameByAddr("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query DID's name by address force

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetDIDNameByAddrForce} from "hashkeydid-js"
// DID address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryDIDNameByAddrForce(){
    let did = await GetDIDNameByAddrForce("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query DID's address based on different blockchain

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetBlockChainAddress} from "hashkeydid-js"
// tokenId: 1222
// coinType: 1 eg: 1->ethereum, 137->polygon
async function QueryBlockChainAddress(){
    let did = await GetBlockChainAddress(1222, 1)
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's content hash

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetContentHash} from "hashkeydid-js"
// tokenId: 1222
async function QueryContentHash(){
    let contentHash = await GetContentHash(1222)
}
```
{% endtab %}

{% tab title="Go" %}

{% endtab %}
{% endtabs %}

Query tokenId's public key

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetPublicKey} from "hashkeydid-js"
// tokenId: 1222
async function QueryGetPublicKey(){
    let publicKey = await GetPublicKey(1222)
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's key/value pair

{% tabs %}
{% tab title="JS" %}
```javascript
import {Text} from "hashkeydid-js"
// tokenId: 1222
// key: name
async function QueryText(){
    let value = await Text(1222, "name")
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query DID's metadata image url

{% tabs %}
{% tab title="JS" %}
<pre class="language-javascript"><code class="lang-javascript"><strong>import {GetMetadataImageByDIDName} from "hashkeydid-js"
</strong>// did: terro.key
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryMetadataImageByDIDName(){
    let imageUrl = await GetMetadataImageByDIDName("terro.key", {"blockTag": 16513266})
}

</code></pre>
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's metadata image url

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetMetadataImageByTokenId} from "hashkeydid-js"
// tokenId: 1222
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryMetadataImageByTokenId(){
    let imageUrl = await GetMetadataImageByTokenId(1222, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query DID's avatar url.&#x20;

we'v already provided four blockchains info about `chainList` pramater

```json
{
    "1":      {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"},
    "137":    {"network": "Polygon", "RPC": "https://matic-mainnet-archive-rpc.bwarelabs.com"},
    "8217":   {"network": "Klaytn", "RPC": "https://klaytn01.fandom.finance"},
    "210425": {"network": "PlatON", "RPC": "https://openapi2.platon.network/rpc"},
}
```

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetAvatarByDIDName} from "hashkeydid-js"
// did: terro.key
// chainList(optional): {"1": {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"}}
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryAvatarByDIDName(){
    let avatarUrl = await GetAvatarByDIDName("terro.key", {"1": {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"}}, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's avatar url

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetAvatarByTokenId} from "hashkeydid-js"
// tokenId: 1222
// chainList(optional): {"1": {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"}}
// overrides(optional): {"blockTag": 16513266} (search from block number 16513266)
async function QueryAvatarByTokenId(){
    let avatarUrl = await GetAvatarByTokenId(1222, {"1": {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"}}, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

Query tokenId's metadata

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetMetadata} from "hashkeydid-js"
// tokenId: 1222
async function QueryMetadata(){
    let metadata = await GetMetadata(1222)
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}











