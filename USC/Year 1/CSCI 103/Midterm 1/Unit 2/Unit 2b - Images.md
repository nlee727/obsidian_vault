### Interpreting Multidimensional Data
C++ uses the policy that the elements of the lowest dimension are next to each other while the highest dimension is farthest apart in memory
PROJECT 2^

### Passing Multidimensional Arrays
- Formal Parameter: Must Give dimensions of all but first dimension

### Linearization of 2d Arrays
- Given an array of NR Rows and NC Columns
- How to access x\[i\]\[j\]
- Every time you skip a row you are skipping n columns things
- Once you are at the row, you take j steps in
Therefore, Start+ (i * NC +j) * sizeof(int)

### Linearization of 3d Arrays
- Given an array of NP Planes, NR Rows, NC Columns
- Starts at lowest dimension
Start + (p * NR * NC + i * NC + j) * sizeof(int)


# Images
## Grayscale Images
Most grayscale images use 8-bit numbers for reach pixel
- unsigned char (0=black, 255=white)
