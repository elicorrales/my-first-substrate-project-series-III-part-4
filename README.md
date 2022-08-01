# my-first-substrate-project-series-III-part-4

# Rust(Ink!) Smart Contract for Substrate

Smart contracts for Substrate blockchains are written in Ink!, which is essentially Rust with some helpful traits.  

https://ink.substrate.io/why-rust-for-smart-contracts/  
  
https://github.com/paritytech/ink  
  
# Why ```contract-cargo``` ?  

If you went through our Series II (the Solana blockchain), remember we had to install a new cargo command to handle eBPF contract binaries.  
  
Similarly, in order to:  
- build the WASM binary,
- then deploy(for Subtrate the term is ```upload```),  
- and we will also have to ```instantiate``` an instance of the contract on the blockchain,
- and finally we will want to ```call``` (invoke a command from our contract)

then you will need ```contract-cargo```.  
  
## Install ```cargo-contract```  

```
sudo apt install -y binaryen
```
``` 
cargo install cargo-dylint dylint-link
```
```
cargo install --force --locked cargo-contract
```

## Prep

For this series on Substrate, we have the following directory structure for our project lessons:   

${HOME}/<your-path-to-a-place-to-gather-all-subtrate-stuff-plus-your-project-code/
  
    my-first-project/  
  
        my-first-client/
            client.js
        my-first-smart-contract/
            <here is where we will be for now>

Go to ```my-first-smart-contract``` directory and do a ```cargo contract new helloworld```.  
  
Then go into the directory (```helloworld```).  

```
$ tree
.
├── README.md
├── my-first-client
│   ├── client.js
│   └── node_modules -> /home/IamDeveloper/.nvm/versions/node/v18.6.0/lib/node_modules/
└── my-first-smart-contract
    └── helloworld
        ├── Cargo.toml
        └── lib.rs
```
  

Do a ```cargo +nightly contract build --release```.  
  
A final, successful(?) output (remains to be seen since we have not yet tried to deploy(```upload```) it to the local substrate node):  
```
   Compiling ink_storage v3.3.0
   Compiling ink_lang v3.3.0
   Compiling helloworld v0.1.0 (/tmp/cargo-contract_N0AQ9k)
   Compiling metadata-gen v0.1.0 (/tmp/cargo-contract_N0AQ9k/.ink/metadata_gen)
    Finished release [optimized] target(s) in 1m 34s
     Running `target/ink/release/metadata-gen ''`
 [5/5] Generating bundle

Original wasm size: 17.6K, Optimized: 0.4K

The contract was built in RELEASE mode.

Your contract artifacts are ready. You can find them in:
/home/IamDeveloper/MySoftwareProjects/blockchain/rust/rust-substrate-blockchain-projects/my-first-substrate-projects/my-first-project-prep-lesson/my-first-smart-contracts/helloworld/target/ink

  - helloworld.contract (code + metadata)
  - helloworld.wasm (the contract's code)
  - metadata.json (the contract's metadata)
```

