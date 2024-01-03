# mfcobol-ports - Directory
COBOL source code compatible with 'Micro Focus COBOL' ported from the web

| Description                | Original Source                                                                                                        | Directory      | Minimum Micro Focus Version |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------- | -------------- | --------------------------- |
| Eliza in Micro Focus COBOL | [eliza.cbl](https://github.com/OCamlPro/gnucobol-contrib/blob/master/samples/eliza/eliza.cbl)                          | eliza          | 9.0                         |
| Prime Machine              | [prime_machiine.cob](https://github.com/OCamlPro/gnucobol-contrib/blob/master/samples/prime_machine/prime_machine.cob) | prime_machine  | -                           |
| raylib_painter             | [CobolDraw.cob](https://github.com/OCamlPro/gnucobol-contrib/blob/master/samples/raylib_painter/CobolDraw.cob)         | raylib_painter | -                           |
| cobsha3                    | [cobsha3](https://github.com/OCamlPro/gnucobol-contrib/tree/master/samples/cobsha3)                                    | cobsha3        | -                           |


## Eliza

Changes made:
 - Removed used of non-portable "FUNCTION SUBSTITUTE"
   - Change either to "INSPECT REPLACING" if src/target are same length or custom section

## prime_machine

Changes made:

 - USAGE is reserved word and cannot be used a symbolic constant
 - remove >>elif, as it is not portable and use >>evaluate
 - replace non-portable copybook reference and use local 78' items

## raylib_painter

Changes made;
  
  - 'values' on redefines is non-portable
  - literal's passed to 'C' need to be zero terminated, so use z"..."
  - convert "returning omitted" to CALL no-return-code
  - add .h and used h2py to weed-out any parameter call'ing issues
  - fix memory leak in 'C' code

## cobsha3

Changes made:

 - binary-int is not portable changed to binary-long
 - use of "" within quotes is not portable
 - replace FUNCTION STORED-CHAR-LENGTH with portable code
 - program-id's with "-" in the name are non-portable, so change them
 - create a shared library

TODO:
 - Convert TES* source to a proper unit test