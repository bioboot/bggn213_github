# Class 6: R functions
Barry (PID: 911)

My first function :-)

``` r
add <- function(x, y=1, z=0) {
  x + y + z
}
```

Can I just use it?

``` r
add(1,1)
```

    [1] 2

``` r
add(x=1, y=100)
```

    [1] 101

``` r
add(x=c(100,1,100), y=1)
```

    [1] 101   2 101

``` r
add(10)
```

    [1] 11

``` r
add(10, y=10)
```

    [1] 20

``` r
add( 1, 1, z=1)
```

    [1] 3

# A second function

Let’s try something more intresting:

``` r
#generate_dna <- function() {
  
bases <- c("A", "C", "G", "T")
sequence <- sample(bases, size=5, replace = TRUE)
```

That is my wee working snipet now I can make it into a function.

``` r
generate_dna <- function(length) {
  bases <- c("A", "C", "G", "T")
  sequence <- sample(bases, size=length, 
                     replace = TRUE)
  return(sequence)
}
```

``` r
generate_dna(10)
```

     [1] "G" "A" "A" "T" "G" "G" "A" "C" "T" "G"

``` r
aa <- unique(bio3d::aa.table$aa1)[1:20]
```

Write a protein generating function

``` r
generate_protein <- function(length) {
  
  aa <- unique(bio3d::aa.table$aa1)[1:20]
  sequence <- sample(aa, size=length, replace = T)
  sequence <- paste(sequence, collapse = "")
  return(sequence)  
  
}
```

``` r
generate_protein(6)
```

    [1] "FMWPKS"

Generate random protein sequences of length 6 to 12

``` r
answer <- sapply(6:12, generate_protein)
answer
```

    [1] "GQGQFD"       "GPVYCDR"      "KPSQPPDG"     "IYDTYSRHD"    "VDYFVYYICF"  
    [6] "VDMYQEQEGKS"  "IYYLIWDIGYVD"

``` r
cat( paste(">id.", 6:12, "\n", answer, sep=""), sep="\n" )
```

    >id.6
    GQGQFD
    >id.7
    GPVYCDR
    >id.8
    KPSQPPDG
    >id.9
    IYDTYSRHD
    >id.10
    VDYFVYYICF
    >id.11
    VDMYQEQEGKS
    >id.12
    IYYLIWDIGYVD
