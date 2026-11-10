# Warning: test secret only

The files in this folder hold a known test secret. It is published in this repository, so anyone can read it. It protects nothing. The library secret, the sample salts and the aggregator private key are all public. So anyone can unlock the hash values in any hash file locked with the sample public key, even one made with a real secret build. A hash file can also be made with the sample salt file and these secret builds. For such a file, anyone can test guesses of patient details against its hash values.

* `linkja_secret.h` holds the library secret in plain text.
* `liblinkjacrypto.dylib` (macOS) and `linkjacrypto.dll` (Windows) are secret builds of the crypto library made with that test secret.

Use them only to try out linkja-hashing with the sample data in `../../hashing`.

Never use them for a real project. A real project compiles its own secret build. It then deletes its own `linkja_secret.h` once the build is given to the sites. See the [linkja-crypto README](https://github.com/MRAIA-ORG/linkja-crypto) for the steps.
