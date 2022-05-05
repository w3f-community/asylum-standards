# UPDATETEMPLATE

Update a [template](../entities/template.md) according to [proposal](../entities/proposal.md)

## ARGUMENTS

Pass appropriate arguments to corresponding extrinsic of the asylum-core pallet directly or via connection lib. Let's describe arguments as JSON scheme:

```json
{
  "template-id": {
    "type": "number",
    "description": "The id of the template to be destroyed"
  },
    "proposal-id": {
    "type": "number",
    "description": "The id of the proposal"
  }
}
```

## EXAMPLE

```json
{
  "template-id": 42,
  "proposal-id": 314
}
```