# linkja-test-data

## Warning

The secret files in `crypto/secret` hold a known test secret. It is published in this repository, so it protects nothing. The library secret, the sample salts and the aggregator private key are all public. So anyone can unlock the hash values in any hash file locked with the sample public key, even one made with a real secret build. If such a file was also made with the sample salt file and these secret builds, anyone can test guesses of patient details against it.

* `crypto/secret/linkja_secret.h` holds the library secret in plain text.
* `crypto/secret/liblinkjacrypto.dylib` (macOS) and `crypto/secret/linkjacrypto.dll` (Windows) are secret builds of the crypto library made with that test secret.

The sample salt file (`hashing/salt.txt`) and the aggregator private key (`matching/private-agg.key`) are published test secrets too.

Never use these files for a real project. A real project compiles its own secret build. See the [linkja-crypto README](https://github.com/MRAIA-ORG/linkja-crypto) for the steps.

Test data to be used when trying out Linkja software

* crypto - contains copies of the linkja-crypto library for Windows or macOS.  Two versions exist:
	* public - used by the linkja-salt-engine and linkja-matching programs, this does not contain the library secret.
	* secret - used by linkja-hashing, this has the test library secret embedded in it. See the warning at the top.
* hashing - sample data file, public key, and salt file to be used for hashing
* matching - private key to be used for matching
* salt-engine - a main file containing test sites (`sites.csv`), and a supplemental file for adding sites to an existing project (`extra-sites.csv`).