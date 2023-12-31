# POLY PROOF Module 3 Circuits with Circom

This project provides examples of zero-knowledge proof circuits implemented using the Circom language. It includes templates for basic logic gates (AND, OR, NOT) and a more complex circuit template (Multiplier2) that demonstrates generating, proving, and verifying zero-knowledge proofs for arithmetic operations.

## Circuit Templates

### AND Gate

The AND gate template computes the logical AND of two input signals.

```circom
template AND(){
   signal input a;
   signal input b;
   signal output out;
   out <== a*b;
}
### OR Gate
The OR gate template computes the logical OR of two input signals.

circom
Copy code
template OR(){
   signal input a;
   signal input b;
   signal output out;
   out <== a+b-a*b;
}
### NOT Gate
The NOT gate template computes the logical NOT of an input signal.

circom
Copy code
template NOT(){
   signal input in;
   signal output out;
   out <== 1+in-2*in;
}
### Multiplier2 Circuit
The Multiplier2 circuit template checks that the output signal Q after input signals a, b, x, and y.

### Quick Start
Prerequisites:

Node.js and npm installed
Hardhat installed globally: npm install -g hardhat
Compile Circuits

To compile the Multiplier2 circuit and generate the out file with circuit intermediaries and the MultiplierVerifier.sol contract:

shell
Copy code
npx hardhat circom
Prove and Deploy

To deploy the MultiplierVerifier.sol contract, generate a proof, and verify the proof:

shell
Copy code
npx hardhat run scripts/deploy.ts
This script performs the following steps:

Deploys the MultiplierVerifier.sol contract
Generates a proof from circuit intermediaries using generateProof()
Generates calldata with generateCallData()
Calls verifyProof() on the verifier contract with calldata
### Owner Name
Modified Owner: Avinash - 22BCT10100
