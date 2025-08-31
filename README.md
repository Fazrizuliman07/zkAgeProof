# zkAgeProof: Zero-Knowledge Age Verification

## Summary
zkAgeProof is a zkApp that allows users to prove they are above a certain age (e.g., 18+) without revealing their full date of birth.  
The proof is generated off-chain and verified on-chain through the Soundness Layer, ensuring privacy and trust.

## Problem
Most websites and apps require users to disclose sensitive personal information such as date of birth for age verification.  
This creates privacy risks, potential for data leaks, and unnecessary data sharing.

## Solution
zkAgeProof leverages zero-knowledge proofs to let a user prove their age is above a threshold without revealing exact details.  
- The user submits their date of birth locally (off-chain).  
- A zkProof is generated confirming whether the age > threshold.  
- The Soundness Layer validates the proof on-chain.  
- The application receives only a "YES/NO" verification, not the raw data.

## Technical Architecture
- **Client**: User inputs their date of birth locally.  
- **ZK Circuit**: Generates proof (e.g., age >= 18).  
- **Soundness Layer**: Onchain attestation validates the proof.  
- **Verifier App**: Third-party apps (social platforms, KYC-lite services) consume the attestation for access control.

## Benefits
- Protects user privacy by hiding sensitive personal data.  
- Reduces risk of centralized data leaks.  
- Easy to integrate into apps requiring age checks (social media, online games, KYC-lite platforms).

## How to Run (Local)
1. Download the repo.  
2. Open `client/index.html` in your browser (double click).  
3. Select your date of birth.  
4. You will only see **“Verified 18+”** or **“Not verified”**.

## Roadmap
- Replace simple JS check with a **ZK circuit** (Circom/Noir).  
- Verify proofs on-chain via **Soundness Layer** attestation.  
- Provide a simple verifier smart contract and end-to-end demo.

## Status
Early PoC (demo only). No personal data is stored.

---
*Submitted for the Soundness Dev Program*
