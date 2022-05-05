# CREATETEMPLATE

Creates a new [template](../entities/template.md)

## ARGUMENTS

Pass appropriate arguments to corresponding extrinsic of the asylum-core pallet directly or via connection lib. Let's describe arguments as JSON scheme:

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
  "template-name": {
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

## EXAMPLE

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