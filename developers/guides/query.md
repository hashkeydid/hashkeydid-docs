# Query

### Query DID name

Query user's DID name by `tokenId`, you can note the specific block by `overrides` parameter.

{% tabs %}
{% tab title="JS" %}
```javascript
import {TokenId2Did} from "hashkeydid-js"
// tokenId: 1222
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryTokenIdByDid(){
    let did = await TokenId2Did(1222, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

### Query DID's tokenId

Query user's tokenId by DID name, you can note the specific block by `overrides` parameter.

{% tabs %}
{% tab title="JS" %}
```javascript
import {Did2TokenId} from "hashkeydid-js"
// did name: terro.key
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryDidByTokenId(){
    let tokenId = await Did2TokenId("terro.key", {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}

### Query DID name by address

Query DID name by DID address when you set resolver is true, you can note the specific block by  `overrides/opts` parameter.

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetDIDNameByAddr} from "hashkeydid-js"
// DID address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryDIDNameByAddr(){
    let did = await GetDIDNameByAddr("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}
```go
import (
	"math/big"
	"github.com/ethereum/go-ethereum/accounts/abi/bind"
	"github.com/ethereum/go-ethereum/common"
	hashkeydid "github.com/hashkeydid/hashkeydid-go"
)

func QueryDIDNameByAddr(){
	core, err := hashkeydid.NewDIDCore(
		hashkeydid.DefaultPlatONUrl, 
		hashkeydid.DefaultDIDContractAddr, 
		hashkeydid.DefaultDIDResolverContractAddr,
	)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	name, err := core.GetDIDNameByAddr(opts, common.HexToAddress("0xa060C1C3807059027Ca141EFb63f19E12e0cBF0c"))
}
```
{% endtab %}
{% endtabs %}

### Query DID's name by address force

Query DID name by DID address force even if the resolver is false, you can note the specific block by `overrides/opts` parameter.

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetDIDNameByAddrForce} from "hashkeydid-js"
// DID address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryDIDNameByAddrForce(){
    let did = await GetDIDNameByAddrForce("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}
```go
import (
	"math/big"
	"github.com/ethereum/go-ethereum/accounts/abi/bind"
 	"github.com/ethereum/go-ethereum/common"
	hashkeydid "github.com/hashkeydid/hashkeydid-go"
)

func QueryDIDNameByAddrForce(){
	core, err := hashkeydid.NewDIDCore(
		hashkeydid.DefaultPlatONUrl, 
		hashkeydid.DefaultDIDContractAddr, 
		hashkeydid.DefaultDIDResolverContractAddr,
	)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	name, err := core.GetDIDNameByAddrForce(opts, common.HexToAddress("0xa060C1C3807059027Ca141EFb63f19E12e0cBF0c"))
}
```
{% endtab %}
{% endtabs %}

### Query DID's address by DID name

Query DID address by DID name,  you can note the specific block by `overrides/opts` parameter.

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetAddrByDIDName} from "hashkeydid-js"
// DID name: herro.key
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryAddrByDIDName(){
    let addr = await GetAddrByDIDName("herro.key", {"blockTag": 16513266})
}j

```
{% endtab %}

{% tab title="Go" %}
```go
```
{% endtab %}
{% endtabs %}

### Query DID's KYC information

Query user's KYC information by `tokenId`, `KYCProvider`, `KYCId and` note the specific block by  `overrides/opts` parameter.

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetKYCInfo} from "hashkeydid-js"
// tokenId: 1222
// KYCProvider: 0xdeDBB6048b0B9107a21d81E345afe0789229Dbac
// KYCId: 1
// overrides: {"blockTag": 16513266} (search in block number 16513266)
async function QueryKYCInfo(){
    let info = await GetKYCInfo(1222, "0xdeDBB6048b0B9107a21d81E345afe0789229Dbac", 1, {"blockTag": 16513266})
}

```
{% endtab %}

{% tab title="GO" %}
```go
import (
	"math/big"
	"github.com/ethereum/go-ethereum/accounts/abi/bind"
	"github.com/ethereum/go-ethereum/common"
	hashkeydid "github.com/hashkeydid/hashkeydid-go"
)

func QueryKYCInfo(){
	core, err := hashkeydid.NewDIDCore(
		hashkeydid.DefaultPlatONUrl, 
		hashkeydid.DefaultDIDContractAddr, 
		hashkeydid.DefaultDIDResolverContractAddr,
	)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	kycInfo, err := core.GetKYCInfo(opts, 1222, common.HexToAddress("0xdeDBB6048b0B9107a21d81E345afe0789229Dbac"),1)
}
```
{% endtab %}
{% endtabs %}

### Query DID's metadata avatar image url

Query DID user's metadata avatar url, you can note the specific block by `overrides/opts` parameter.

{% tabs %}
{% tab title="JS" %}
<pre class="language-javascript"><code class="lang-javascript"><strong>import {GetMetadataImageByDIDName} from "hashkeydid-js"
</strong>// did: terro.key
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryMetadataImageByDIDName(){
    let metadataAvatarUrl = await GetMetadataImageByDIDName("terro.key", {"blockTag": 16513266})
}

</code></pre>
{% endtab %}

{% tab title="GO" %}
```go
import (
	"math/big"
	"github.com/ethereum/go-ethereum/accounts/abi/bind"
	hashkeydid "github.com/hashkeydid/hashkeydid-go"
)

func QueryMetadataImageByDIDName(){
	core, err := hashkeydid.NewDIDCore(
		hashkeydid.DefaultPlatONUrl, 
		hashkeydid.DefaultDIDContractAddr, 
		hashkeydid.DefaultDIDResolverContractAddr,
	)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	metadataAvatarUrl, err := core.GetMetadataAvatarByDIDName(opts, "terro.key")
}
```
{% endtab %}
{% endtabs %}

### Query DID's resolver avatar url.&#x20;

we'v already provided four blockchains info about `chainList` pramater, you can also customize the chain information according to the following format

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
// overrides(optional): {"blockTag": 16513266} (search in block number 16513266)
async function QueryResolverAvatarByDIDName(){
    let avatarUrl = await GetAvatarByDIDName("terro.key", {"1": {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"}}, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}
```go
import (
	"math/big"
	"github.com/ethereum/go-ethereum/accounts/abi/bind"
	hashkeydid "github.com/hashkeydid/hashkeydid-go"
)

func QueryResolverAvatarByDIDName(){
	core, err := hashkeydid.NewDIDCore(
		hashkeydid.DefaultPlatONUrl, 
		hashkeydid.DefaultDIDContractAddr, 
		hashkeydid.DefaultDIDResolverContractAddr,
	)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	// ChainList: nil
	avatarUrl, err := core.GetAvatarByDIDName(opts, "terro.key", nil)
}
```
{% endtab %}
{% endtabs %}

### Query DID's address based on different blockchain

User can bond the address for different chains to DID account, and use the following method to query address information with `coinType` parameter.

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











