# SUBMITTEMPLATECHANGEPROPOSAL

Submit template change [proposal](../entities/proposal.md)

## ARGUMENTS

Pass appropriate arguments to corresponding extrinsic of the asylum-core pallet directly or via connection lib. Let's describe arguments as JSON scheme:

```json
{
  "author": {
    "type": "string",
    "description": "Author's address, e.g. CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp"
  },
  "template-id": {
    "type": "number",
    "description": "The id of the template to be updated"
  },
  "changes": {
    "type": Change[],
    "description": "Array of proposed changes"
  },
}
```

## EXAMPLE

```json
{
  "author": "CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp",
  "template-id": 42,
  "changes": [
      Add({
          "type": "2D",
          "interpretations": [
            {
                "id": "inventory-pixel-2D",
                "src": "hash-of-pixel-2D-source",
                "metadata": "hash-of-pixel-2D-metadata"
            },
            {
                "id": "anime-2D",
                "src": "anime-2D-source",
                "metadata": "anime-2D-metadata"
            }
          ]
      }),
      Modify( {
          "type": "3D",
          "interpretations": [
            {
                "id": "preview-3D",
                "src": "new-preview-3D-source",
                "metadata": "hash-of-pixel-2D-metadata"
            }
          ]
      }),
      RemoveInterpretation({
          "type": "2D",
          "interpretations": [
            {
                "id": "legacy-unused-2D",
                "src": "hash-of-pixel-2D-source",
                "metadata": "hash-of-pixel-2D-metadata"
            }
          ]
      }),
     RemoveInterpretationType({
         "type": "MockTypeForTests"
     })
  ],
}
```