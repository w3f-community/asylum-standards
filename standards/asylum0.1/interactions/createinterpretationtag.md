# CREATEINTERPRETATIONTAG

Сreates a new [interpretation tag](../entities/interpretation-tag.md)

## ARGUMENTS

Pass appropriate arguments to corresponding extrinsic of the asylum-core pallet directly or via connection lib. Let's describe arguments as JSON scheme:

```json
{
  "name": {
    "type": "string",
    "description": "The name of the interpretation tag"
  },
  "metadata": {
    "type": "string",
    "description": "HTTP(s) or IPFS URI. If IPFS, MUST be in the format of ipfs://ipfs/HASH"
  },
}
```

## EXAMPLE

```json
{
  "name": "2D",
  "metadata": "ipfs://ipfs/QmVgs8P4awhZpFXhkkgnCwBp4AdKRj3F9K58mCZ6fxvn3j"
}
```