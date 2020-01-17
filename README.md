# README

## Info:

Feel free to use these lines as you wish. These programs load a graph in main memory as (i) a list of edges, (ii) an adjacency matrix or (iii) an adjacency list.

## To compile:

"gcc edgelist.c -O9 -o edgelist"  
"gcc adjmatrix.c -O9 -o adjmatrix"  
"gcc adjarray.c -O9 -o adjarray"


## To execute:

"./edgelist edgelist.txt"  
"./adjmatrix edgelist.txt"  
"./adjarray edgelist.txt"

"edgelist.txt" should contain the graph: one edge on each line (two unsigned long (nodes' ID) separated by a space).  
The program will load the graph in main memory and then terminate.

## Performance:

- edgelist: up to 500 million edges on my laptop with 8G of RAM. Takes more or less 1.6G of RAM and 25 seconds (I have an SSD hardrive) for 100M edges.
- adjmatrix: up to 200.000 nodes on my laptop with 8G of RAM. Takes more or less 4G of RAM and 10 seconds for 100.000 nodes.
- adjlist: up to 200 million edges on my laptop with 8G of RAM: takes more or less 4G of RAM and 30 seconds for 100M edges.

adjmatrix is much less scallable than the two other programs for sparse graphs. adjmatrix uses O(n^2) memory (n^2 boolean values (note that adjmatrix uses 1 byte to encode a boolean value and not 1 bit...)), while edgelist uses O(m) (2m unsigned) and adjlist uses O(m+n) (4m+2n unsigned).

## Note:

If the graph is directed (and weighted) with selfloops and you want to make it undirected unweighted without selfloops, use the following linux command line.  
awk '{if ($1<$2) print $1" "$2;else if ($2<$1) print $2" "$1}' net.txt | sort -n -k1,2 -u > net2.txt

## Initial contributors

Maximilien Danisch  
September 2017  
http://bit.ly/danisch  
maximilien.danisch@gmail.com

