Perform a SHA256 hash of a SHA256 hash of Base16 data and then reverse the byte order. 
```sh
$ bx bitcoin256 --help
```
```
Usage: bx bitcoin256 [-h] [--config VALUE] [BASE16]                      

Info: Perform a SHA256 hash of a SHA256 hash of Base16 data and then     
reverse the byte order.                                                  

Options (named):

-c [--config]        The path to the configuration settings file.        
-h [--help]          Get a description and instructions for this command.

Arguments (positional):

BASE16               The Base16 data to hash. If not specified the data  
                     is read from STDIN.
```
### Example 1
```sh
$ bx bitcoin256 900df00d
```
```
23429b4cc436b2ebd4aa33b904a1e08f195715c34d275e9088ea7b12af3872cd
```
Notice that following commands produce the same result with the exception that the resulting hash [cd7238af...] is in the reverse byte order of the `bitcoin256` command output [...af3872cd]. This is an idiosyncrasy of the reference implementation.
```sh
$ bx sha256 900df00d | bx sha256
```
```
f0ebe3bd55115e573ba35c2b1b65a923ff64c7a548d0deab73f9314754a9149d
cd7238af127bea88905e274dc31557198fe0a104b933aad4ebb236c44c9b4223
```
### Example 2
piped commands
```sh
$ bx base16-encode "L'homme est libre au moment qu'il veut l'être." | bx bitcoin256
```
```
4c27686f6d6d6520657374206c69627265206175206d6f6d656e7420717527696c2076657574206c27ea7472652e
1b3254eb9c7d042d9be9882b62deaa51da4538a31f3f9c76e3eef41367a7b246
```