# skills
ERC-1155 Token-Based Credentialing System

Tokens in ERC-1155 have a 256-bit id and a 256-bit value for each id.

This particular set of tokens is meant to represent skills and a framework for associating skills with xDAI users.

Token types are represented as JSON-LD `@context`s. The mill maintains a mapping of 16-bits to `@context` URIs.

Of the 256-bits:

- the first 128-bits are a UUID-v0
- the next eight bits are `0` if it is a fungible token
- skill tokens are `0x0101${incremental token id}`
- for each skill, there is an accompanying fungible token `0x0001${token id}`
- the fungible token represents the number of hours spend execrising that skill
- credential tokens are `0x0102${incremental token id}

The format of the JSON metadata for an ERC-1155 token is:

```javascript
{
  "name": "Javascript",
  "description": "Experience with the Javascript programming language.",
  "image": "ipfs://Qmkhn234…",
  "decimals": 18,
  "properties": { /* any object */ }
}
```

The `properties` for a `skill` will be:

```javascript
{
  context: ['http://schema.org/skills']

}
```