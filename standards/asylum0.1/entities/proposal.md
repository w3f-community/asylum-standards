# Proposal

Template change proposal is a set of proposed changes to template: Add/Modify/Remove [interpretations](interpretation.md)

## Proposal Standard

An proposal MUST adhere to the following standard. Changes will be applied in the order of their array indexes, so they MUST NOT contradicts to each other, i.e. don't try modify already removed interpretation.

```json
{
  "author": {
    "type": "string",
    "description": "Author's address, e.g. CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp"
  },
  "state": {
    "type": ProposalState,
    "description": "Proposal's state: Pending, Approved, Rejected"
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

## Change

A change MUST adhere to the following standard

Add:

```json
{
  "interpretations": {
    "type": (Interpretation, Tag[])[],
    "description": "Array of interpretations to be added"
  },
}
```

Modify:

```json
{
  "interpretations": {
    "type": Interpretation[],
    "description": "Array of interpretations to be modified. Interpretations will replace interpretations with the same id"
  },
}
```

Modify tags:

```json
{
  "interpretation-id": {
    "type": "number",
    "description": "The id of interpretaation to be removed"
  },
  "tags": {
    "type": Tag[],
    "description": "New tag's set"
  }
}
```

Remove interpretation:

```json
{
  "interpretation-id": {
    "type": "number",
    "description": "The id of interpretation to be removed"
  },
}
```



## Examples

```json
{
  "author": "CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp",
  "state": Pending,
  "template-id": 42,
  "changes": [
      Add({
          "interpretations": [
            {
                "id": "inventory-pixel-2D",
                "src": "hash-of-pixel-2D-source",
                "tags": ["inventory-view", "style-pixel", "2D"],
                "metadata": "hash-of-pixel-2D-metadata"
            },
            {
                "id": "anime-2D",
                "src": "anime-2D-source",
                "tags": ["style-anime", "2D"],
                "metadata": "anime-2D-metadata"
            }
          ]
      }),
      Modify({
          "interpretations": [
            {
                "id": "preview-3D",
                "src": "new-preview-3D-source",
                "tags": ["market-preview", "3D"],
                "metadata": "hash-of-pixel-2D-metadata"
            }
          ]
      }),
      ModifyTags({
          "interpretation-id": "intepretation-with-deprecated-tags-id",
          "tags": ["new-tag-1", "new-tag-2"]
      }),
      RemoveInterpretation({
          "interpretation-id": "legacy-unused-2D"
      })
  ],
}
```

## Interactions

- [SUBMITTEMPLATECHANGEPROPOSAL](../interactions/submittemplatechangeproposal.md) - submit a new proposal