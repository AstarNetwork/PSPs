# Nesting NFTs

- **PSP Number:** 61
- **Authors:** [boyswan](https://github.com/boyswan), [Maar-io](https://github.com/Maar-io),
- **Status:** Draft
- **Created:** [2023-05-10]
- **Reference Implementation** [Link to a first reference implementation](https://github.com/rmrk-team/rmrk-ink)

## Summary

An interface for MultiAssets on Non-Fungible Tokens.

## Motivation


## Specification

1. Interfaces
2. Events
3. Types
4. Errors

### Interfaces
This section defines the required interface for this standard.

#### MultiAsset::add_child(parent_token_id: Id, child_nft: ChildNft) -> Result<(), NestingError>

Selector: `0x1d6f5156`, first 4 bytes of `blake2b_256(Nesting::add_child)`
```json

```
### Types
```rust
// AccountId is a 32 bytes Array, like in Substrate-based blockchains.
type AccountId = [u8; 32];
```
```rust
// Id is a 128 bit unsigned integer
type Id = u128;
```
```rust
// ChildNft is a tuple of Child's contract address and child's Id
type ChildNft = (AccountId, Id)
```

### Errors
The suggested methods revert the transaction and return a [SCALE-encoded](https://github.com/paritytech/parity-scale-codec) `Result` type with one of the following `Error` enum variants:

```rust
enum MultiAssetsError {

}
```

## Tests

Check reference implementation

## Copyright

Each PSP must be labeled as placed in the
[public domain](https://creativecommons.org/publicdomain/zero/1.0/).
