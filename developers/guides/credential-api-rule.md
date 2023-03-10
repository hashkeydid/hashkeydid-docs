# Credential API Rule

If you want invoke your own HTTP API to check whether a address is eligible dynamically, you need follow this guide.

## Method

Your API should use http **GET** method

## URL

URL for your API should contains user's 0x address. You could place it in URL or query parameters. And could with other static param like your rule ID. Here's some examples below:

 - https://example.com/api/eligible?address={address}
 - https://example.com/api/eligible/{address}
 - https://example.com/api/eligible?activity=demo&address={address}
 - https://example.com/api/activities/demo/eligible/{address}

## Request Headers / Body

Hashkey DID will send empty request body and no specific headers.

## Response Header

Your should set `Content-Type` to `application/json`, because of we only support JSON format by now. No other specific headers.

## Response Body

Using JSON format in response body, attributes definitions' below:

 - code: integer, you should set it to 200 if API invoke is correct.
 - msg: string, you should set it as error message when code is not 200. Otherwise "ok" is ok.
 - data: boolean, true only when the address is eligible. 

Example Eligible:
```json
{
	"code": 200,
	"msg": "ok",
	"data": true
}
```

Example Not Eligible
```json
{
	"code": 403,
	"msg": "The address is not eligible.",
	"data": false
}
```
## Whitelist

You need to make sure servers for Hashkey DID could access your API, so you could add below IPs to your whitelist.

 - 54.254.70.197
 - 13.215.165.253
 - 18.140.251.108
 - 18.138.89.198
 - 13.228.194.226
 - 18.136.155.107