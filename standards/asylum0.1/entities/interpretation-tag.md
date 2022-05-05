# Interpretation Tag

Interpretation tag is used to give an [interpretation](interpretation.md) a special semantic allowing Game Client to query specific interpretation according to the context. Interpretation tag can describe list of fields, that will be required from the interpretation.

## Interpretation Tag Standard

An interpretation tag MUST adhere to the following standard.

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

## Metadata

An interpretation tag MUST have metadata to describe it and help game developers of the Asylum ecosystem in the best way of leveraging this interpretation tag.

```json
{
  "id": "string",
  "description": {
    "type": "string",
    "description": "Description of the interpretation tag as a whole. Markdown is supported."
  },
  "metadataExtensions":  {
    "fields": [ 
      {
          "name": "string",
          "description": "string"
          "default": "array" | "object" | "int" | "float" | "boolean" | "datetime" | "string",
          "type": "array" | "object" | "boolean" | "datetime" | "string" | "number"
      }
    ]
  }
}
```

## Examples

Interpretation tag :
```json
{
  "name": "sound",
  "metadata": "ipfs://ipfs/QmVgs8P4awhZpFXhkkgnCwBp4AdKRj3F9K58mCZ6fxvn3j"
}
```

Metadata:

```json
{
  "id": "sound",
  "description": "Sound",
  "metadata-extensions":  {
    "fields": [ 
      {
        "name" : "sound-related-parameter",
        "type": "float",
        "description": "sound-related-paramter-description",
      }
    ]
 }
}
```

## Interactions

[CREATEINTERPRETATIONTAG](../interactions/createinterpretationtag.md) - creates a new interpretation tag
