# Solana-NFT-Anchor

Based on the [Mint Your First NFT](https://calyptus.co/lessons/mint-your-first-nft/) lesson, this project shows how to mint your first NFT on the Solana blockchain using [Anchor](https://www.anchor-lang.com/) and [Metaplex](https://www.anchor-lang.com/).

## Table of Contents

- [Solana-NFT-Anchor](#solana-nft-anchor)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
  - [Contributing](#contributing)
  - [Questions](#questions)
  - [License](#license)

## Getting Started

To use this fork, you need to have [yarn](https://yarnpkg.com/getting-started/install), [Anchor](https://www.anchor-lang.com/docs/installation) and the [Solana cli suite](https://solana.com/developers/guides/getstarted/setup-local-development) installed on your machine.

It is highly recommended that you start this project from scratch, following along with the tutorial.

To use the fork, follow the steps outlined below:

1. Clone your forked repo.

```bash
git clone https://github.com/aquental/solana-nft-anchor
```

2. Change directory into the root of your cloned repo and install missing node packages

```bash
yarn install
```

**NOTE:** You must use yarn to install the dependencies. If you use a different package manager, you will run into issues minting the NFT.

3. Build your anchor project.

```bash
anchor build
```

4. List the project deployment keys and copy the address to a clipboard

```bash
anchor keys list
```

```bash
solana_nft_anchor: 3NReB6T8WG254kVxi538V83muxcTDa1CJYR3UUC91idE
```

5. Update your [`Anchor.toml`](Anchor.toml) file, by uncommenting the line blow and adding the address generated in the previous step.

```toml
[programs.devnet] # uncomment below
# solana_nft_anchor = "3NReB6T8WG254kVxi538V83muxcTDa1CJYR3UUC91idE"
```

6. Update your [`lib.rs`](programs/solana-nft-anchor/src//lib.rs) file by adding the the address generated in step 4 to the `declare_id!()` macro

```rust
    // snip
use mpl_token_metadata::{
    pda::{find_master_edition_account, find_metadata_account},
    state::DataV2,
};

declare_id!("3NReB6T8WG254kVxi538V83muxcTDa1CJYR3UUC91idE");
#[program]
pub mod solana_nft_anchor {
    // snip
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Questions

Did you encounter a challenge following the tutorial or running the fork?
Head over to our [learning support](https://discord.com/channels/1130457754826461216/1132978998155165806) channel on our [Discord](https://discord.gg/38KftAhW) or alternatively, raise a ticket.

We are always happy to lend a helping hand

## License

All files within this repository are licensed under the MIT License unless explicitly stated otherwise.

100% Open Source software.

© 2023 [Calyptus] - See [LICENSE](https://opensource.org/license/mit/) for details.

---

**Program Id**: 3NReB6T8WG254kVxi538V83muxcTDa1CJYR3UUC91idE

mint nft tx: https://explorer.solana.com/tx/5TntH3e1ockf1NvkRkxN3tmvkvPYsecjj1RwGJu4HxMUHXvFukgpF9Lohfww2KG62Q3SKhUqnq6KE5BB4HdrfXkH?cluster=devnet

minted nft: https://explorer.solana.com/address/BJ9EReAWitoFfEgk1gjrv8C8NepApyAfDXTvKUsNBQyt?cluster=devnet
