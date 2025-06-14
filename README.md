# Cartesi Coprocessor

The **Cartesi Coprocessor** combines the technologies of [EigenLayer](https://www.eigenlayer.xyz/) and the [Cartesi Machine](https://docs.cartesi.io/machine/) to provide expressive, verifiable off-chain computation for Ethereum smart contracts.

## Overview

This project enables developers to extend the capabilities of Ethereum applications by leveraging Cartesi's RISC-V-based execution environment in conjunction with EigenLayer's AVS (Actively Validated Services) infrastructure. The result is a powerful, modular architecture for off-chain computation with trustless validation.

## Architecture

The Cartesi Coprocessor consists of smart contracts and two primary off-chain components:

- **Coprocessor Operator**  
  A stateless executor that receives and runs Cartesi Machines with a specific input and signs the resulting computation. Operators do not retain any local state between requests.

- **Coprocessor Solver**  
  A coordination agent that listens for computation requests emitted by smart contracts. It orchestrates the execution using a set of Operators, aggregates their BLS signatures on the result, and submits the aggregated proof back on-chain via a callback to the originating contract.

This architecture enables highly parallel, verifiable computation with strong cryptographic guarantees of correctness, without requiring interactive fraud proofs or continual on-chain execution.

## Repository Contents

This repository includes:

- **Docker Compose Environment**  
  A ready-to-use `docker-compose` setup for local development, testing, and iteration.

- **Smart Contracts**  
  Solidity contracts and deployment scripts that compose the Ethereum-side components of the AVS.

- **Holesky Deployment Configuration**  
  Scripts and configuration for deploying to the Holesky Ethereum testnet.

## EigenLayer Compatibility

This project targets the general version of **EigenLayer smart contracts** that supports:

- **Operator Sets**
- **Slashing**

## License

This project is licensed under the **Apache License 2.0 (APLv2)**.

> **Note:** Some components may depend on or interoperate with third-party software from [EigenLayer](https://www.eigenlayer.xyz/) that is separately licensed. Please consult those components’ respective repositories for detailed licensing terms.
