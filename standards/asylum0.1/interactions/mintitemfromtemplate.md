# MINTITEMFROMTEMPLATE

Mint [item](../entities/item.md) from [template](../entities/template.md). Item will have the same set of [interpretations](../entities/interpretation.md) as template has.

## ARGUMENTS

Pass appropriate arguments to corresponding extrinsic of the asylum-core pallet directly or via connection lib. Let's describe arguments as JSON scheme:

```json
{
  "owner": {
    "type": "string",
    "description": "The owner of minted item"
  },
  "template-id": {
    "type": "number",
    "description": "The id of the template"
  },
  "metadata": {
    "type": "string",
    "description": "HTTP(s) or IPFS URI. If IPFS, MUST be in the format of ipfs://ipfs/HASH"
  }
}  
```

## EXAMPLE

```json
{
  "owner": "CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp",
  "template-id": 42,
  "metadata": "ipfs://ipfs/QmavoTVbVHnGEUztnBT2p3rif3qBPeCfyyUE5v4Z7oFvs4"
}  
```