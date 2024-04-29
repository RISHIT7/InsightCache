# AES are of 3 types, depending on the size of the key
> 1) 128 bits -> 10 Rounds
> 2) 192 bits -> 12 Rounds
> 3) 256 bits -> 14 Rounds

## Operations Performed by AES
> 1) Starts with an XOR of the data and the key's 128 bit subpart
> 2) Rounds start from 1 to N-1 composed of
>       - Substitute Bytes
>       - Shift Rows
>       - Mix columns
>       - Add key
> 3) Round N does not have Mix columns, rest is same

## Substitution Rules

> 1) No byte is mapped to itself
> 2) No byte is mapped to its reverse
> 3) Substitution is a lookuptable

## Shift Rows

> 1) First Row doesnt move
> 2) Seoncd Row shifts right by 1
> 3) Thrid Row shifts right by 2
> 4) Forth Row shifts right by 3

## Mix Columns

> 1) Done Using a Matrix Multiplication
> 2) The Matrix is ->
> $
> \begin{equation}
> \begin{array}{ccc}
> 2 & 3 & 1 & 1 \\
> 1 & 2 & 3 & 1 \\
> 1 & 1 & 2 & 3 \\
> 3 & 1 & 1 & 2\\
> \end{array}
> \end{equation}$

## Round Key

> 1) Bitwise XOR Between input matrix and the round key


# Key Expansion Logic

> 1) every round takes 4 words of 128 bits total
> 2) since there are 11 rounds in case of AES-128 we need w[0-3] for round 0, w[4-7] for round 2, ..., there for we need w[40-43] for round 10
> ### Key Exapansion
> - Say the initial key is of 128 bits
> - w[0] = k[0-3], ...
>
> ![AES Key Exapansion Image](images\KeyExpansion.png)
> <p style = "color: rgba(256, 256, 256, 0.2)">Courtesy (Neso Academy)</p>