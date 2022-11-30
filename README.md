### Environment Setup
1. Install Rust from https://rustup.rs/
2. Install Solana v1.13.5 or later from https://docs.solana.com/cli/install-solana-cli-tools#use-solanas-install-tool

### Build and test for program compiled natively
```
cargo build
cargo test
```

### Build and test the program compiled for BPF
```
cargo build-bpf
cargo test-bpf
```

### Deploy to solana-test-validator
```
solana-test-validator
solana config set --url http://127.0.0.1:8899
solana-keygen new -o ./validator-keypair.json
solana-keygen pubkey ./validator-keypair.json
solana config set --keypair ./validator-keypair.json
solana airdrop 100
solana program deploy ./target/deploy/helloworld.so
```