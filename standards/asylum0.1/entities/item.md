# Item

Item is an NFT minted from the particular [template](template.md). Item has the same [interpretation](interpretation.md) list, specified by template at the time of its minting, but can be different in future with [upgrading](../interactions/updatetemplate.md) of template. Owner of item [might not want](../interactions/acceptitemupdate.md) to upgrade his item according to latest upgrades in template. Item inherits properties of the [RMRK's NFT](https://github.com/rmrk-team/rmrk-spec/blob/master/standards/rmrk2.0.0/entities/nft.md).

## Item Standard

An item MUST adhere to the following standard.

```json
{
  "collection": {
    "type": "string",
    "description": "Collection ID, e.g. 0aff6865bed3a66b-ZOMB"
  },
  "owner": {
      "type": "string",
      "description": "Account which owns the NFT. Computed from MINTITEMFROMTEMPLATE interaction."
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

An item MUST have metadata to describe it and help game developers of the Asylum ecosystem in the best way of leveraging this template.

```json
{
  "description": {
    "type": "string",
    "description": "Description of the template as a whole. Markdown is supported."
  }
}
```

## Examples

Item:

```json
{
  "collection": "0aff6865bed3a66b-UltraSuperSword",
  "owner": "CpjsLDC1JFyrhm3ftC9Gs4QoyrkHKhZKtK7YqGTRFtTafgp",
  "metadata": "ipfs://ipfs/QmavoTVbVHnGEUztnBT2p3rif3qBPeCfyyUE5v4Z7oFvs4",
  "interpretations": [
      {
        "id": "inventory-pixel-2D",
        "src": "hash-of-pixel-2D-source",
        "metadata": "hash-of-pixel-2D-source-metadata",
        "tags": ["inventory-view", "2D"]
      },
      {
        "id": "anime-2D",
        "src": "hash-of-anime-2D-source",
        "metadata": "hash-of-anime-2D-metadata",
        "tags": ["2D"]
      }
  ]
}
```

Metadata:

```json
{
  "description": "Item supports two 2D views: inventory pixel and anime",
}
```

## Interactions

- [MINTITEMFROMTEMPLATE](../interactions/mintitemfromtemplate.md) - mints item from template
- [TRANSFERITEM](../interactions/transferitem.md) - transfers item
- [BURNITEM](../interactions/burnitem.md) - burn item
- [ACCEPTITEMUPDATE](../interactions/acceptitemupdate.md) - accept the update to the latest template state
