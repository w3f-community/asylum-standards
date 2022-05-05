# Interpretation

Interpretation is the description of the media resource used to interpretate the [template](template.md) in some context. To describe such context interpretation MUST be assosiated with the unique set of [tags](interpretation-tag.md). This set of tags defining the format of tnterpretation's metadata.

## Interpretation Standard

An interpretation MUST adhere to the following standard.

```json
{
  "id": {
    "type": "string",
    "description": "The id of the interpretation"
  },
  "src": {
    "type": "string",
    "description": "HTTP(s) or IPFS URI. If IPFS, MUST be in the format of ipfs://ipfs/HASH"
  },
  "tags": {
    "type": Tag[],
    "description": "Array of supported tags"
  },  
  "metadata": {
    "type": "string",
    "description": "HTTP(s) or IPFS URI. If IPFS, MUST be in the format of ipfs://ipfs/HASH"
  },
}
```

## Metadata

An interpretation MUST have metadata to describe it and help game developers of the Asylum ecosystem in the best way of leveraging this interpretation.

```json
{
  "description": {
    "type": "string",
    "description": "Description of the interpretation as a whole. Markdown is supported."
  },
  "name": {
    "type": "string",
    "description": "Name of the interpretation, e.g. 'inventory-pixel-2D'."
  }
}
```

## Examples

Interpretation:

```json
{
  "id": "inventory-pixel-2D",
  "src": "hash-of-pixel-2D-source",
  "tags": ["inventory-view", "2D"],
  "metadata": "hash-of-pixel-2D-metadata"
}
```

Metadata:

```json
{
  "description": "You may use this interpretation in the inventory context of pixel 2D game",
  "name": "inventory-pixel-2D"
}
```