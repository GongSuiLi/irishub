# iriscli bank account

## Description

This command is used for querying balance information of certain address.

## Usage:

```
iriscli bank account [address] [flags] 
```

 

## Flags

| Name,shorthand | Type   | Required | Default               | Description                                                  |
| -------------- | ------ | -------- | --------------------- | ------------------------------------------------------------ |
| -h, --help     |        | False    |                       | help for account                                             |
| --chain-id     | String | False    |                       | Chain ID of tendermint node                                  |
| --height       | Int    | False    |                       | Block height to query, omit to get most recent provable block |
| --ledger       | String | False    |                       | Use a connected Ledger device                                |
| --node         | String | False    | tcp://localhost:26657 | <host>:<port> to tendermint rpc interface for this chain     |
| --trust-node   | String | False    | True                  | Don't verify proofs for responses                            |



## Global Flags

| Name,shorthand        | Default        | Description                                 | Required | Type   |
| --------------------- | -------------- | ------------------------------------------- | -------- | ------ |
| -e, --encoding string | hex            | String   Binary encoding (hex \|b64 \|btc ) | False    | String |
| --home string         | /root/.iriscli | Directory for config and data               | False    | String |
| -o, --output string   | text           | Output format (text \|json)                 | False    | String |
| --trace               |                | Print out full stack trace on errors        | False    |        |

## Examples

### Query your account in trust-mode

```
 iriscli bank account iaa19aamjx3xszzxgqhrh0yqd4hkurkea7f646vaym --trust-node=true
```

After that, you will get the detail info for the account.

```
{

  "address": "iaa19aamjx3xszzxgqhrh0yqd4hkurkea7f646vaym",

  "coins": [

    "50iris"

  ],

  "public_key": {

    "type": "tendermint/PubKeySecp256k1",

    "value": "AzlCwiA5Tvxwi7lMB/Hihfp2qnaks5Wrrgkg/Jy7sEkF"

  },

  "account_number": "0",

  "sequence": "1"

}

```
### Common Issue


If you query an wrong account, you will get the follow information.
```
iriscli bank account iaa19aamjx3xszzxgqhrh0yqd4hkurkea7f6d429zz
ERROR: decoding bech32 failed: checksum failed. Expected 46vaym, got d429zz.
```
If you query an empty account, you will get the follow error. But don't panic when you see the following error. 
```
iriscli bank account iaa1kenrwk5k4ng70e5s9zfsttxpnlesx5psh804vr
ERROR: No account with address iaa1kenrwk5k4ng70e5s9zfsttxpnlesx5psh804vr was found in the state.
Are you sure there has been a transaction involving it?
```


## Extended description

Query your account in iris network. If you want to create a validator, you should use `iriscli bank account` to make sure 
that your balance is above 0.


​           
