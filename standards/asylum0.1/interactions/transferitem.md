# TRANSFERITEM

Transfer [item](../entities/item.md) to new owner(in [RMRK's SEND](https://github.com/rmrk-team/rmrk-spec/blob/master/standards/rmrk2.0.0/interactions/send.md) context)

## ARGUMENTS

Pass appropriate arguments to corresponding extrinsic of the asylum-core pallet directly or via connection lib. Let's describe arguments as JSON scheme:

```json
{
  "template-id": {
    "type": "number",
    "description": "The id of the template"
  },
  "item-id": {
    "type": "number",
    "description": "The id of the item to be transfered"
  },
  "destination": {
      "type": "string",
      "description": "New owner of the item"
  }
}
```

## EXAMPLE

```json
{
  "template-id": 42,
  "item-id": 453,
  "destination": "CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp"
}