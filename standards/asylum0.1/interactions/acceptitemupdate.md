# ACCEPTITEMUPDATE

Accept all updated [proposed](submittemplatechangeproposal.md) by [template's](../entities/template.md) owner after succesful [template's update](updatetemplate.md). If not accepted, all updated will be in pending state.

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
    "description": "The id of the item to be updated"
  }
}
```

## EXAMPLE

```json
{
  "template-id": 42,
  "item-id": 453
}