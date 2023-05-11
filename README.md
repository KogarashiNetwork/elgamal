# ElGamal Encryption 
[![CI](https://github.com/KogarashiNetwork/elgamal/actions/workflows/ci.yml/badge.svg)](https://github.com/KogarashiNetwork/elgamal/actions/workflows/ci.yml) [![crates.io badge](https://img.shields.io/crates/v/zero-elgamal.svg)](https://crates.io/crates/zero-elgamal) [![GitHub license](https://img.shields.io/badge/license-GPL3%2FApache2-blue)](#LICENSE) [![dependency status](https://deps.rs/crate/zero-elgamal/0.1.11/status.svg)](https://deps.rs/crate/zero-elgamal/0.1.11)

This crate provides additive homomorphic ElGamal encryption over jubjub curve and also supports fully `no_std` and [`parity-scale-codec`](https://github.com/paritytech/parity-scale-codec).

## Scheme
Alice has balance $a$ and public key $b$.  
She generates the randomness $r$ and computes encrypted balance $(g^r, g^a * b^r)$.  
When Bob transfers $c$ to Alice, he generates the randomness $r'$ and computes encrypted transfer amount $(g^{r'}, g^c * b^{r'})$.  
The sum of encrypted balance and transfer amount is folloing.

$$
(g^{r + r'}, g^{a + c} * b^{r + r'})
$$
