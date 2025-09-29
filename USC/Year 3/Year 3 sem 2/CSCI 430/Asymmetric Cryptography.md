Everyone has two keys:
- Public key K1 that everyone knows
- Private key K2 that only the owner knows

Requirements for asymmetric crypto protocol
- Easy to generate a pair of matching keys
- Easy to encrypt/decrypt with each key
- Hard to calculate one key if you know another
- Hard to break the encryption without knowing the decryption key
- Either of the keys in the pair can be used to encrypt/decrypt
Greater functionality of symmetric crypto
- Non-repudiation, prove to a 3rd party that Alice sent the party and cannot fake it
- However 1,500 times slower

### Asymmetric Algorithms
#### RSA
Look for a set of operations to that we can encrypt with one key and decrypt with the other
$$
D_{K2}(E_{K1}(M))=M
$$
Galois Field - Do all operations mod n
Modular exponentiation - M^key mod n

We want
$$
(M^xmod(n))^ymod(n)=M^{x\times y}
$$
Choose two prime numbers p and q of equal length
Compute n=p * q
and $\phi(n)=(p-1)(q-1)$
choose private key x relatively prime to $\phi(n)$

Using extended Euclidean calculate y, which is inverse of x mod $\phi (n)$
Publish $y$ and $n$, remember x
Encryption:
$$E_{x}(M)=M^x mod(N)$$
Decryption:

Factoring large numbers is computationally intensive. Generally factoring time of large number n increases exponentially with each binary digit added to $n$
