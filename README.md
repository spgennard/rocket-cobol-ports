# mfcobol-ports - Directory
COBOL source code compatible with 'Micro Focus COBOL' ported from the web

| Description                | Original Source                                                                                                        | Directory     | Minimum Micro Focus Version |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------- | --------------------------- |
| Eliza in Micro Focus COBOL | [eliza.cbl](https://github.com/OCamlPro/gnucobol-contrib/blob/master/samples/eliza/eliza.cbl)                          | eliza         | 9.0                         |
| Prime Machine              | [prime_machiine.cob](https://github.com/OCamlPro/gnucobol-contrib/blob/master/samples/prime_machine/prime_machine.cob) | prime_machine | -                           |



# Eliza

Changes made:
 - Removed used of non-portable "FUNCTION SUBSTITUTE"
   - Change either to "INSPECT REPLACING" if src/target are same length or custom section

# prime_machine

Changes made:

 - USAGE is reserved word and cannot be used a symbolic constant
 - remove >>elif, as it is not portable and use >>evaluate
 - replace non-portable copybook reference and use local 78' items