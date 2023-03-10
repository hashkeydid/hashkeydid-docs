# Query

### Query DID name

Example code was used to query user's DID name by `tokenId and`you can note the specific block by `overrides` parameter.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDID} from "hashkeydid";
// tokenId: 1222
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryDidByTokenId(){
    const did = await NewHashKeyDID("https://openapi2.platon.network/rpc");
    const did_name = await did.TokenId2Did(1222, {blockTag: 16513266});
    console.log(did_name)
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

func QueryDidByTokenId(){
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search at block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	did, _ := core.GetDidByTokenId(opts, big.NewInt(1222))
	fmt.Println(did)
}
```
{% endtab %}
{% endtabs %}

### Query DID tokenId

Code was used to query user's tokenId by DID name and you can note the specific block by `overrides` parameter.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDID} from "hashkeydid";
// did name: terro.key
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryTokenIdByDid(){
    const did = await NewHashKeyDID("https://openapi2.platon.network/rpc");
    const tokenId = await did.Did2TokenId("terro.key", {blockTag: 16513266})
    console.log(tokenId);
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

func QueryTokenIdByDid(){
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search at block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	tokenId, _ := core.GetTokenIdByDid(opts, "terro.key")
	fmt.Println(tokenId)
}
```
{% endtab %}
{% endtabs %}

### Query DID name by address

Code was used to query DID name by DID address when you set resolver is true. you can note the specific block by  `overrides/opts` parameter.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDIDResolver} from "hashkeydid";
// DID address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryDIDNameByAddr(){
    const resolver = await NewHashKeyDIDResolver("https://openapi2.platon.network/rpc");
    const did_name = await resolver.GetDIDNameByAddr("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {blockTag: 16513266});
    console.log(did_name);
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
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	name, _ := core.GetDIDNameByAddr(opts, common.HexToAddress("0xa060C1C3807059027Ca141EFb63f19E12e0cBF0c"))
	fmt.Println(name)
}
```
{% endtab %}
{% endtabs %}

### Query DID name by address force

Querying DID name by DID address force even if the resolver is false. you can note the specific block by `overrides/opts` parameter.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDIDResolver} from "hashkeydid";
// DID address: 0xteDBB6048b0B9107a21d81E345afe0789229DbTs
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryDIDNameByAddrForce(){
    const resolver = await NewHashKeyDIDResolver("https://openapi2.platon.network/rpc");
    const did_name = await resolver.GetDIDNameByAddrForce("0xteDBB6048b0B9107a21d81E345afe0789229DbTs", {blockTag: 16513266});
    console.log(did_name);
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
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	name, _ := core.GetDIDNameByAddrForce(opts, common.HexToAddress("0xa060C1C3807059027Ca141EFb63f19E12e0cBF0c"))
	fmt.Println(name)
}
```
{% endtab %}
{% endtabs %}

### Query DID address by DID name

Querying DID address by DID name. you can note the specific block by `overrides/opts` parameter.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDID} from "hashkeydid";
// DID name: herro.key
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryAddrByDIDName(){
    const did = await NewHashKeyDID("https://openapi2.platon.network/rpc");
    const addr = await did.GetAddrByDIDName("herro.key", {blockTag: 16513266});
    console.log(addr)
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

func QueryAddrByDIDName(){
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search at block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	addr, _ := core.GetAddrByDIDName(opts, "terro.key")
	fmt.Println(addr)
}

```
{% endtab %}
{% endtabs %}

### Query DID KYC information

Querying user's KYC information by `tokenId`, `KYCProvider`, `KYCId and` note the specific block by  `overrides/opts` parameters.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDID} from "hashkeydid";
// tokenId: 1222
// KYCProvider: 0xdeDBB6048b0B9107a21d81E345afe0789229Dbac
// KYCId: 1
// overrides: {"blockTag": 16513266} (search at block number 16513266)
async function QueryKYCInfo(){
    const did = await NewHashKeyDID("https://openapi2.platon.network/rpc");
    const kyc = await did.GetKYCInfo(1222, "0xdeDBB6048b0B9107a21d81E345afe0789229Dbac", 1, {blockTag: 16513266});
    console.log(kyc);
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
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	kycInfo, _ := core.GetKYCInfo(opts, big.NewInt(1222), common.HexToAddress("0xdeDBB6048b0B9107a21d81E345afe0789229Dbac"),big.NewInt(1))
	fmt.Println(kycInfo)
}
```
{% endtab %}
{% endtabs %}

### Query DID metadata avatar image url

Querying DID user's metadata avatar url and you can note the specific block by `overrides/opts` parameter.

{% tabs %}
{% tab title="TypeScript" %}
<pre class="language-typescript"><code class="lang-typescript"><strong>import {NewHashKeyDIDResolver} from "hashkeydid";
</strong>// did: terro.key
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryMetadataImageByDIDName(){
    const resolver = await NewHashKeyDIDResolver("https://openapi2.platon.network/rpc");
    const metadata = await resolver.GetMetadataImageByDIDName("terro.key", {blockTag: 16513266});
    console.log(metadata)
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
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	metadataAvatarUrl, _ := core.GetMetadataAvatarByDIDName(opts, "terro.key")
	fmt.Println(metadataAvatarUrl)
}
```
{% endtab %}
{% endtabs %}

### Query DID resolver avatar url.&#x20;

We'v already provided four blockchains info about `chainList` pramater, you can also customize the chain information according to the following format

```json
{
    "1":      {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"},
    "137":    {"network": "Polygon", "RPC": "https://matic-mainnet-archive-rpc.bwarelabs.com"},
    "1284":   {"network": "Moonbeam", "RPC": "https://moonbeam.public.blastapi.io"},
    "8217":   {"network": "Klaytn", "RPC": "https://klaytn01.fandom.finance"},
    "210425": {"network": "PlatON", "RPC": "https://openapi2.platon.network/rpc"},
}
```

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDIDResolver} from "hashkeydid";
// did: terro.key
// chainList(optional): {"1": {"network": "Ethereum", "RPC": "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7"}}
// overrides(optional): {"blockTag": 16513266} (search at block number 16513266)
async function QueryResolverAvatarByDIDName(){
    const resolver = await NewHashKeyDIDResolver("https://openapi2.platon.network/rpc");
    const avatar = await resolver.GetAvatarByDIDName("terro.key", {blockTag: 16513266}, "https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7");
    console.log(avatar);
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
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search in block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	// ChainList: nil
	avatarUrl, _ := core.GetAvatarByDIDName(opts, "terro.key")
	fmt.Println(avatarUrl)
}
```
{% endtab %}
{% endtabs %}

### Query DID address based on different blockchain

User can bond the address for different chains to DID account, and use the following method to query address information with `coinType` parameter.

{% tabs %}
{% tab title="TypeScript" %}
```typescript
import {NewHashKeyDIDResolver} from "hashkeydid";
// tokenId: 1222
// coinType: 1 eg: 1->ethereum, 137->polygon
async function QueryBlockChainAddress(){
    const resolver = await NewHashKeyDIDResolver("https://openapi2.platon.network/rpc");
    const addr = await resolver.GetBlockChainAddress(1222, 1);
    console.log(addr);
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

func QueryBlockChainAddress(){
	core, _ := hashkeydid.NewDIDCore(hashkeydid.DefaultPlatONUrl)
	// opts parameter is optional, it's for search at block number 16513266
	opts := &bind.CallOpts{BlockNumber: new(big.Int).SetUint64(16513266)}
	addr, _ := core.GetBlockChainAddress(opts, 1222, big.NewInt(1))
	fmt.Println(avatarUrl)
}

```
{% endtab %}
{% endtabs %}











