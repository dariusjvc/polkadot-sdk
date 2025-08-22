# Dilithium Post-Quantum Signature PoC for Substrate-based Blockchain

## Overview

This repository contains a Proof of Concept (PoC) implementation for integrating Dilithium post-quantum signatures into a Substrate-based blockchain.

The goal of this PoC is to explore the feasibility of verifying Dilithium signatures via a custom JSON-RPC endpoint before allowing the submission of on-chain transactions.

The work is based on a modified version of the `polkadot-sdk` Solochain template.

## Important Disclaimer

This is strictly a Proof of Concept (PoC).  
It is not production-ready and must not be used in any production environment.  
The current implementation does not provide cryptographic security guarantees and should only be used for educational or experimental purposes.

## Key Features

- A Dilithium signature is generated off-chain using the `pqcrypto-dilithium` library.
- A custom RPC method (`dilithium_verify`) is implemented in the node to verify the Dilithium signature.
- Transactions are only submitted to the blockchain if the signature is successfully verified.

## Why Not for Production?

1. No on-chain verification: The signature is only checked via RPC, not by the blockchain protocol itself.
2. Potential bypass risks: Clients could bypass the RPC and submit extrinsics directly to the node.
3. No key management: Private keys are handled in an insecure way for demonstration purposes.
4. No formal security audit has been conducted.

## Intended Use

- Research
- Experimentation
- Demonstration of post-quantum cryptography concepts in Substrate

## Future Work (if moving towards production)

- Implement on-chain signature verification in the runtime (pallet level).
- Use Dilithium keys for extrinsic signing, replacing or complementing existing cryptography.
- Conduct security audits and ensure compliance with cryptographic best practices.

## Acknowledgements

Built on top of:
- Polkadot SDK
- pqcrypto
