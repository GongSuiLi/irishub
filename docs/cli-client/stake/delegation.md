# iriscli stake delegation

## Description

Query a delegation based on address and validator address

## Usage

```
iriscli stake delegation [flags]
```
Print help messages:
```
iriscli stake delegation --help
```

## Unique Flags

| Name, shorthand       | Default                    | Description                                                          | Required |
| --------------------- | -------------------------- | -------------------------------------------------------------------- | -------- |
| --address-delegator   |                            | [string] Bech address of the delegator                               | Yes      |
| --address-validator   |                            | [string] Bech address of the validator                               | Yes      |

## Examples

Query a validator
```
iriscli stake delegation --address-validator=iva106nhdckyf996q69v3qdxwe6y7408pvyv3hgcms --address-delegator=iaa106nhdckyf996q69v3qdxwe6y7408pvyvyxzhxh

```

After that, you will get detailed info of the delegation between specified validator and delegator.

```txt
Delegation
Delegator: iaa13lcwnxpyn2ea3skzmek64vvnp97jsk8qrcezvm
Validator: iva15grv3xg3ekxh9xrf79zd0w077krgv5xfzzunhs
Shares: 200.0000000
Height: 290
```
