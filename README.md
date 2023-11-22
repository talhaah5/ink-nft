# ink! Non Fungible Token



## Setting up the Ink Project

The easiest way to bootstrap an Ink project currently is to install the "Hello World" contract of Ink, named Flipper. With Flipper installed, we can build upon what is already included and not have to worry about configuration and compile scripts — these are provided in Flipper.

Note: Both Substrate and Ink are in rapid development and are not yet feature complete, therefore the smart contract environment, and the smart contract code itself, will most likely change as Parity get nearer to a final release of the framework.

To jump start our Ink project fetch Flipper using cargo:

```
# fetch the Flipper Ink contract

cargo contract new flipper
```

Flipper provides us a project boilerplate needed to start writing the smart contract. Included is:

The folder structure and configuration metadata of the project
A bare-bones Flipper contract in src/lib.rs, that simply “flips” a boolean value between true and false via a flip() method, and gets this value on-chain using the get() method. We will be replacing this file with the NFT contract
The Rust specific Cargo.toml file, outlining the project dependencies and module metadata, a .gitignore file, and a build.sh file. The build.sh file is what we run to compile our smart contract, resulting in a compiled .wasm file of the contract, a JSON abstraction of the contract, and more. We’ll explore the built contract further down.

*__Note__: Now is a good time to check out src/lib.rs to get a feel of the contract syntax.*

Let’s change the name flipper to a more suitable name: nftoken. Amend the following:

* `flipper/` folder name to /nftoken
* `Cargo.tom`l: Change `[package] name` and `[lib] name` to `nftoken`
* `build.sh`: amend `PROJNAME=nftoken`

Also, ensure we have permissions to run `nftoken/build.sh`:
```
cd nftoken
chmod +x build.sh
```
Lastly, add the /nftoken folder to a VS Code Workspace, and we are ready to start writing.


## Summary

We have completed the Ink smart contract deployment journey, from Installation to Instantiation on chain. As a brief summary, let’s visit the various pieces that made the process possible:

* Bootstrapping of the basic `Flipper` Ink contract to obtain the Ink boilerplate, including environment configuration and `build.sh` file
* Writing the NFToken contract adhering to Rust concepts and conventions, with minting, transferring and approval functionalities, along with event emission
* Testing via the `tests` module, before compiling the contract with `build.sh`
* Deploying, instantiating and testing function calls via the Polkadot JS client, connected to your local Substrate dev chain
