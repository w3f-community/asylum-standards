# BURNITEM

Burn [item](../entities/item.md)

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
    "description": "The id of the item to be burned"
  }
}
```

## EXAMPLE


```json
{
  "template-id": 42,
  "item-id": 453
}