# Template

Template in the Asylum terms is such kind of "NFT collection" where the [items](item.md) have identical [interpretations](interpretation.md) set. Template inherits properties of the [RMRK's Collection](https://github.com/rmrk-team/rmrk-spec/blob/master/standards/rmrk2.0.0/entities/collection.md). Template interpretations set can be updated. See interactions at the bottom of this page.

## Template Standard

A template MUST adhere to the following standard.

```json
{
  "max": {
    "type": "number",
    "description": "How many NFTs will ever belong to this collection. 0 for infinite."
  },
  "owner": {
    "type": "string",
    "description": "Owner's address, e.g. CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp. Can be address different from minter to assign ownership to other entity on creation."
  },
  "name": {
    "type": "string",
    "description": "Name by which to represent the token in wallets and UIs, e.g. ZOMB"
  },
  "metadata": {
    "type": "string",
    "description": "HTTP(s) or IPFS URI. If IPFS, MUST be in the format of ipfs://ipfs/HASH"
  },
  "interpretations": {
      "type": Interpretation[],
      "description": "The list of supported interpretation types and interpretations for these types"
  }
}
```
## Metadata

A template MUST have metadata to describe it and help game developers of the Asylum ecosystem in the best way of leveraging this template.

```json
{
  "description": {
    "type": "string",
    "description": "Description of the template as a whole. Markdown is supported."
  }
}
```

## Examples

Collection:

```json
{
  "max": 100,
  "issuer": "CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp",
  "symbol": "SWORD",
  "metadata": "ipfs://ipfs/QmVgs8P4awhZpFXhkkgnCwBp4AdKRj3F9K58mCZ6fxvn3j",
  "interpretations": [
    {
      "id": "inventory-pixel-2D",
      "src": "hash-of-pixel-2D-source",
      "tags": ["inventory-view", "style-pixel", "2D"],
      "metadata": "hash-of-pixel-2D-metadata"
    },
    {
      "id": "anime-2D",
      "src": "hash-of-anime-2D-source",
      "tags": ["style-anime", "2D"],
      "metadata": "hash-of-anime-2D-metadata"
    }
  ]
}
```

Metadata:

```json
{
  "description": "Template supports two 2D views: inventory pixel and anime"
}
```

## Interactions

- [CREATETEMPLATE](../interactions/createtemplate.md) - creates a new template
- [DESTROYTEMPLATE](../interactions/destroytemplate.md) - destroy a template
- [UPDATETEMPLATE](../interactions/updatetemplate.md) - update a template
