Extract the payment address of an encrypted private key (BIP38).
```sh
$ bx ek-to-address --help
```
```
Usage: bx ek-to-address [-h] [--config VALUE] PASSPHRASE [EK_PRIVATE_KEY]

Info: Extract the payment address of an encrypted private key (BIP38).   

Options (named):

-c [--config]        The path to the configuration settings file.        
-h [--help]          Get a description and instructions for this command.

Arguments (positional):

PASSPHRASE           The passphrase that was used to generate the        
                     intermediate passphrase token or to encrypt the     
                     encrypted private key.                              
EK_PRIVATE_KEY       The encrypted private key from which to extract the 
                     payment address. If not specified the key is read   
                     from STDIN. 
```
See also [ek-to-ec](bx-ek-to-ec).
### Example 1
mainnet
```sh
$ bx ek-to-address "my passphrase" 6PYXCdvtrs4NN1TjUYbGS5Sd2gjsVsDm7GttqERRWvRjWDsrhQfJeEHrg5
```
```
1z5KLQyPycih1Tpx9jTYfuhHQkNsP7fd4
```
### Example 2
incorrect passphrase
```sh
$ bx ek-to-address "i forgot" 6PYXCdvtrs4NN1TjUYbGS5Sd2gjsVsDm7GttqERRWvRjWDsrhQfJeEHrg5
```
```
The passphrase is incorrect.
```
### Example 3
piped input
```sh
$ echo 6PYXCdvtrs4NN1TjUYbGS5Sd2gjsVsDm7GttqERRWvRjWDsrhQfJeEHrg5 | bx ek-to-address "my passphrase"
```
```
6PYXCdvtrs4NN1TjUYbGS5Sd2gjsVsDm7GttqERRWvRjWDsrhQfJeEHrg5 
1z5KLQyPycih1Tpx9jTYfuhHQkNsP7fd4
```
### Example 4
round trip
```sh
$ bx ec-to-ek "my passphrase" 261fc32e9f29c70e3d898aa7db028c81ede0658e8ff8ffab8160073c048ae83f | bx ek-to-address "my passphrase"
```
```
6PYXCdvtrs4NN1TjUYbGS5Sd2gjsVsDm7GttqERRWvRjWDsrhQfJeEHrg5
1z5KLQyPycih1Tpx9jTYfuhHQkNsP7fd4
```
### Example 5
uncompressed
```sh
$ bx ek-to-address "my passphrase" 6PRPDbKfv3A45QPPfEtvcxM4oA6ShVL7t72VP74P1W3JEUHPrZXNy39FKe
```
```
1NNhf5AifHmYXw1cJmbdjkyv9DQFGGaw57
```
### Example 6
testnet
```sh
$ bx ek-to-address "my passphrase" 8EzHSxX3sfZp6NjYUdt7fZAPCKByrFDS12PHfdexFLSaSAfM7wM7tw3Hof
```
```
mgW2cPVxD13yU7wSfihqNb829QM5iGf9PL
```
### Example 7
testnet, uncompressed
```sh
$ bx ek-to-address "my passphrase" 8EsMUV3Z5A9m8eA28nSYECHAmKmy4YsyCYpGNvzHocFJBFhVYZARNfrfnt
```
```
n2tex8FhUKCoK3VE2La1ZgCF1CzxABVgdz
```
### Example 8
multiplied: lot/sequence
```sh
$ bx ek-to-address "my passphrase" 6PoJB3hjqER7KJDeo69pfX3ttV5DPaQPEf4pZEwhNYjTjqMdvif5qfE34S
```
```
1LoMVBxYZuzZZfTckU3JRccwFCMJYP3WRg
```
### Example 9
multiplied
```sh
$ bx ek-to-address "my passphrase" 6PnUht3dP5Jdcp1B7NGqkEoBw5Ja2wWEeQMDRHqLNrBG4Rqo59eVfMd98B
```
```
1DeDt7odeJqJvquJ6obEZfH1hfJHMvnURa
```
### Example 10
multiplied: uncompressed
```sh
$ bx ek-to-address "my passphrase" 6PfM4jsmgX1veYaiBXqqDe3J8hFtAriohdNGjPfrbt7aQ8H53nijYN6svW
```
```
1MydksvfdWNXM1KnVTS8A78M4b78aJcL1W
```
### Example 11
multiplied: testnet
```sh
$ bx ek-to-address "my passphrase" 8FEMBzS4QWPwxyzrYJxHwzSrdNzroFiQjkAnpf51xcPPXkTvqGrD8bVq68
```
```
mtABBAtcTLGZhxNupNZcPaVLZetzHVWgAp
```
### Example 12
multiplied: testnet, uncompressed
```sh
$ bx ek-to-address "my passphrase" 8F7FpHwGgCmZag3nViwdDJTcRUVSZDiyp362gLWisvHDtMQkyC6JJuFhVX
```
```
n2Vb3w1eSXon87oQD2QVz2LfvahqVhBXKV
```