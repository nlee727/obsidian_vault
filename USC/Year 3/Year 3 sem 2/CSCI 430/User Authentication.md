#### Using One-Way Hashes
- Storing hashed plaintext passwords and username on a server
#### Attacks on password Auth
- Dictionary Attack - guessing passwords
    - Attackers has access and has the hashes of passwords
    - Offline: Guess any password on the server by comparing guesses to a list of precomputes hashed of popular pass
    - Online: Guess a specific user's password by trying popular passwords manually
- Personal information attack
    - Online: Guess about a specific user they have information on
- Reuse Attack
    - Steal a password from one server try it at other servers
- Sniff password from the network
- Social engineering

### Using Salt
- To resist dictionary attacks use salt with a password in hashing
    - A random number assigned to each user separately
    - Salt is stored in clear in the password table
- During authentication salt is combined with the password to produce hash value
- Salt makes offline dictionary attacks hard
    - Slow hash function limits attacker's guessing speed

### Shared-Key Authentication
Challenge-response protocol
- Server sends random number R
- Client encrypts with shared key, sends back
or
- Server sends random number R, encrypted with shared key
- Client decrypts, sends back
or
- Server sends random number R encrypted with shared key
- Client decrypts, sends back R-1, encrypted with shared key