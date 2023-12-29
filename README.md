# mfcobol-ports - Directory
COBOL source code compatible with 'Micro Focus COBOL' ported from the web

| Description                | Original Source                                                                               | Directory | Minimum Micro Focus Version |
| -------------------------- | --------------------------------------------------------------------------------------------- | --------- | --------------------------- |
| Eliza in Micro Focus COBOL | [eliza.cbl](https://github.com/OCamlPro/gnucobol-contrib/blob/master/samples/eliza/eliza.cbl) | eliza     | 9.0                         |



# Eliza

Changes made:
 - Removed used of non-portable "FUNCTION SUBSTITUTE"
   - Change either to "INSPECT REPLACING" if src/target are same length or custom section

# prime_machine
 - USAGE is reserved word and cannot be used a symbolic constant