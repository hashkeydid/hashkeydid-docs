# Query

Query tokenId's all authorized addrs

{% tabs %}
{% tab title="JS" %}
```javascript
import {GetAuthorizedAddrs} from "hashkeydid-js"
// tokenId:1222
// {"blockTag": 16513266}: search from block number 16513266
async function QueryAuthorizedAddrs(){
    let addrs = await GetAuthorizedAddrs(1222, {"blockTag": 16513266})
}
```
{% endtab %}

{% tab title="GO" %}

{% endtab %}
{% endtabs %}





