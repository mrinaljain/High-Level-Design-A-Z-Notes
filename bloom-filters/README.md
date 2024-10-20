# Bloom Filters  [ NO means NO ]

Approximate datastructure that can be used to check non-existance.


Working
: It uses MOD function to map all the items on a filter. 0, 1 is used to map

Redis can be used  to create Bloom filter

#### It gives 2 responses for the search querry
- Item is NOT present
- Item MAYBE present.

> Means there is no case of 100 % surety of present.


### Advantage

- Space efficient


### DisAdvantage

- False Positive rate is more and more as size increases.


### Practical Usage

- only when there are nno delete operations.
- when only require nnot present 