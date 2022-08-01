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
  


