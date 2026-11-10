# Warning: test secret only

The files in this folder hold a known test secret. It is published in this repository, so anyone can read it. It protects nothing. The library secret, the sample salts and the aggregator private key are all public. So anyone can unlock the hash values in a hash file made with these files and the sample public key. With the sample salt file too, anyone can test guesses of patient details against those hash values.

* `linkja_secret.h` holds the library secret in plain text.
* `liblinkjacrypto.dylib` (macOS) and `linkjacrypto.dll` (Windows) are secret builds of the crypto library made with that test secret.

Use them only to try out linkja-hashing with the sample data in `../../hashing`.

Never use them for a real project. A real project compiles its own secret build. It then deletes its own `linkja_secret.h` once the build is given to the sites. See the [linkja-crypto README](https://github.com/MRAIA-ORG/linkja-crypto) for the steps.
