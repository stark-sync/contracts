# StarkSync Contracts

StarkSync is a active liquidity manager for starknet



### Important Commands

Install rust
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Check rust version
```
rustc --version
```

Install scarb
```
curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
```

Check scarb version
```
scarb --version
```
Install **starkli**
```
curl https://get.starkli.sh | sh
starkliup
```

Check **starkli** version
```
starkli --version
```
# Local Deployment With Katana

Install Katana 
```
git clone https://github.com/dojoengine/dojo
cd dojo
cargo install --path ./crates/katana --locked --force
```



1. Create a new env file `testnet.env` and copy `sample.testnet.env` content. You can replace values if you are using different RPC or path for keys is different.

2. run `source testnet.env` to export env variables to your terminal. you can verify if values are set correctly using
```
echo ${STARKNET_ACCOUNT}
``` 

# How to declare contract
```
starkli declare target/dev/<CONTRACT_NAME>.sierra.json --compiler-version 2.1.0
```

# How to deploy contract
```
starkli deploy <CLASS_HASH> <CONSTRUCTOR_ARGS>
```





# How to call contract methods

1. To call view functions, use **call** keyword, for example

```
starkli call 0x03d568de0f4e151ed97a196e7585cae03be68b8d01c3d5af2e19c7aa4bb07202 get
```

2. To call writable functions, use **invoke** keyword, for example

```
 starkli invoke 0x03d568de0f4e151ed97a196e7585cae03be68b8d01c3d5af2e19c7aa4bb07202 set 7
```

## Important Facts

- In Cairo, a string is a collection of characters stored in a `felt252`. Strings can have a maximum length of 31 characters.
- field elements are integers in the range between `0 <= x < P`, where P is a very large prime number, currently `P = 2^{251} + 17 * 2^{192} + 1`


# Starknet foundry commands

Declare a contract

```
sncast --profile <profile-name> declare --contract-name 
<contract-name>
```

Deploy a contract

```
sncast --profile testnet1 deploy --class-hash <class-hash> --constructor-calldata 10000000000  0 0x032aee2a95f251a984a391fb2919757a9074065f3c12b010a142c9fd939e933
```


# Other Useful commands

1. Run `scarb --offline build` to build a project without updating dependencies.
