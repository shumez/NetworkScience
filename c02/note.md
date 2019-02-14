<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c02
Author: 	shumez <https://github.com/shumez>
Created: 	2019-02-13 17:10:6
Modified: 	2019-02-14 19:18:44
-----
Copyright (c) 2019 shumez
-->

# [02] Graph Theory

## [02-01] The Bridges of Königsberg

[![fig-2-1][fig-2-1]][fig-2-1]

([Alexanderson, G., 2006])



## [02-02] Networks and Graphs

- \(N\) *num of nodes*, *size* of the network
- \(L\) *num of links*, (2, 4)

[![fig-2-2][fig-2-2]][fig-2-2]

<!-- <iframe src="http://networksciencebook.com/images/ch-02/video-2-1.m4v"> -->

## [02-03] Degree, Average Degree and Degree Distribution

*degree*

### Degree

\(k_i\): degree of \(i\)-th node 

\(k_1=2, k_2=3, k_3=2, k_4=1 \)

\[ L = \frac{1}{2} \sum_{i=1}^N k_i \] (2.1)


### Average Degree

undirected

\[ \langle k \rangle = \frac{1}{N} \sum_{i=1}^N k_j = \frac{2L}{N} \] (2.2)

directed

- \(k_i^{in}\): incoming degree
- \(k_i^{out}\): outgoing degree

\[ k_i = k_i^{in} + k_i^{out} \] (2.3)


\[ L = \sum_{i=1}^N k_i^{in} = \sum_{i=1}^N k_i^{out} \] (2.4)


\[ \langle k^{in} \rangle = \frac{1}{N} \sum_{i=1}^N k_i^{in} = \langle k^{out} \rangle = \frac{1}{N} \sum_{i=1}^N k_i^{out} = \frac{L}{N} \] (2.5)


### Degree Distribution

\( p_k \): *degree distribution*, a randomly selected node in the network has degree \(k\)

\[ \sum_{k=1}^\infty p_k = 1 \] (2.6)

\[ p_k = \frac{N_k}{N} \] (2.7)

- \(N_k\): num of degree-k nodes

\[ \langle k \rangle = \sum_{k=0}^\infty kp_k \] (2.8)


[![fig.2.3][fig-2-3]][fig-2-3]


[![fig.2.4][fig-2-4]][fig-2-4]



## [02-04] Adjacency Matrix

*adjacenct matrix*: N rows, N cols

\( A_{ij} = \begin{cases} 1 &\text{there is a link} \\ 0 &\text{there is not} \end{cases} \) 


undirected

\[ k_i = \sum_{j=1}^N A_{ji} = \sum_{j=1}^N A_{ji} \] (2.9)


directed

\[ k_i^{in} = \sum_{j=1}^N A_{ij}, \\ k_i^{out} = \sum_{j=1}^N A_{ji} \]
(2.10)


\[ 2L = \sum_{i=1}^N k_i^{in} = \sum_{i=1}^N k_i^{out} = \sum_{ij}^N A_{ij} \] (2.11)

[![fig.2.5][fig-2-5]][fig-2-5]



## [02-05] Real Networks are Sparse

\[ L_{max} = \frac{N(N-1)}{2} \] (2.12)

in a *complete graph* of size \(N\)

[![fig.2.6][fig-2-6]][fig-2-6]

real networks 

[![fig.2.7][fig-2-7]][fig-2-7]



## [02-06] Weighted Networks

\[ A_{ij} = w_{ij} \]


### Metcalfe’s Law: the Value of a Network

*Metcalfe's law*:

val \(\propto N^2 \) 

([Gilder, G., 1993])

[![fig.2.8][fig-2-8]][fig-2-8]



## [02-07] Bipartite Networks


*bipartite graph* (*bigraph*) :

NO U-U / V-V links

[![fig.2.9][fig-2-9]][fig-2-9]


([Goh, K.I., 2007])

[![fig.2.10][fig-2-10]][fig-2-10]


[![fig.2.11][fig-2-11]][fig-2-11]



## [02-08] Paths and Distances


*path length*


[![fig.2.12][fig-2-12]][fig-2-12]


### Shortest Path

*distance*: \(d_{ij}\) shortest path 

undirected, \( d_{ij} = d_{ji} \)

directed, \( d_{ij} \neq d_{ji} \)


[![fig.2.13][fig-2-13]][fig-2-13]

- shortest path (*Geodesic path* \(d\))
- *diamter* (\(d_{max}\))
- *average path length* (\(\langle d \rangle\))
- *cycle* 
- *Eulerian path*: transverse each link exactly once
- *Hamiltonian path*: visit each node exactly 


### Box 2.4 Number of Shortest Parths Between Two Nodes

\(N_{ij}\) (num of shortest paths)
\(d_{ij}\) (distance)
\(A_{ij}\) (adjacency mat)


\(d_{ij} = 1\) if direct link, \(A_{ij} = 1\)

\(d_{ij} = 2 \) if path of length two, \(A_{ik}A_{kj} = 1\)

num of \(d_{ij}=2\) paths between \(i\) and \(j\) is 

\[ N_{ij}^{(2)} = \sum_{k=1}^N A_{ik}A_{jk} = A_{ij}^2 \]


\(d_{ij} = d\), \(A_{ik}\cdots A_{lj} = 1\)

\[ N_{ij}^{(d)} = A_{ij}^d \]


### Network Diameter

*diameter* \(d_{max}\): max shortest path 

for larger networks, determined using the *BFS algorithm*


### Average Path Length

*average path length* \(\langle d \rangle \)

\[ \langle d \rangle = \frac{1}{N(N-1)} \sum_{i,j = 1,N; i \neq j} \]
(2.14)


### Box 2.5 Breadth-First Search (BFS) Algorithm

[![fig.2.14][fig-2-14]][fig-2-14]



## [02-09] Connectedness

*bridge*

[![fig.2.15][fig-2-15]][fig-2-15]


### Box 2.6 Finding the Connected Components of a Network











<style type="text/css">
	img{width: 50%; float: right;}
</style>


[Network Science]: http://networksciencebook.com/ "Albert-László Barabási, Network Science"

[02]: http://networksciencebook.com/chapter/2 "Graph Theory"

[02-01]: http://networksciencebook.com/chapter/2#bridges "The Bridges of Königsberg"

[fig-2-1]: http://networksciencebook.com/images/ch-02/figure-2-1.jpg "fig.2.1 The Bridges of Königsberg"

[Alexanderson, G., 2006]: https://www.ams.org/journals/bull/2006-43-04/S0273-0979-06-01130-X/S0273-0979-06-01130-X.pdf "Alexanderson, G., 2006. About the cover: Euler and Königsberg’s Bridges: A historical view. Bulletin of the american mathematical society, 43(4), pp.567-573."


[02-02]: http://networksciencebook.com/chapter/2#networks-graphs "Networks and Graphs"

[fig-2-2]: http://networksciencebook.com/images/ch-02/figure-2-2.jpg "fig.2.2 Different Networks, Same Graph"

[02-03]: http://networksciencebook.com/chapter/2#degree "Degree, Average Degree and Degree Distribution"

[fig-2-3]: http://networksciencebook.com/images/ch-02/figure-2-3.jpg "fig.2.3 Degree Distribution"

[fig-2-4]: http://networksciencebook.com/images/ch-02/figure-2-4.jpg "fig.2.4 Degree Distribution of a Real Network "

[02-04]: http://networksciencebook.com/chapter/2#matrix "Adjacency Matrix"

[fig-2-5]: http://networksciencebook.com/images/ch-02/figure-2-5.jpg "fig.2.5 The Adjacency Matrix"


[02-05]: http://networksciencebook.com/chapter/2#real-networks "Real Networks are Sparse"

[fig-2-6]: http://networksciencebook.com/images/ch-02/figure-2-6.jpg "fig.2.6 Complete Graph"

[fig-2-7]: http://networksciencebook.com/images/ch-02/figure-2-7.jpg "fig.2.7 The Adjacency Matrix is Sparse"

[02-06]: http://networksciencebook.com/chapter/2#weighted-networks "Weighted Networks"

[Gilder, G., 1993]: https://scholar.google.co.jp/scholar?hl=en&num=20&as_sdt=0%2C5&q=Gilder%2C+G.%2C+1993.+Metcalfe’s+law+and+legacy.+Forbes+ASAP%2C+13%2C+p.1993.&btnG= "Gilder, G., 1993. Metcalfe’s law and legacy. Forbes ASAP, 13, p.1993."

[fig-2-8]: http://networksciencebook.com/images/ch-02/figure-2-8.jpg "fig.2.8 Metcalfe’s Law"

[02-07]: http://networksciencebook.com/chapter/2#bipartite-networks

[fig-2-9]: http://networksciencebook.com/images/ch-02/figure-2-9.jpg "fig.2.9 Bipartite Network"

[Goh, K.I., 2007]: https://www.pnas.org/content/104/21/8685

[fig-2-10]: http://networksciencebook.com/images/ch-02/figure-2-10.jpg "fig.2.10 Human Disease Network"

[fig-2-11]: http://networksciencebook.com/images/ch-02/figure-2-11.jpg "fig.2.11 Tripartite Network"

[02-08]: http://networksciencebook.com/chapter/2#paths "Paths and Distances"

[fig-2-12]: http://networksciencebook.com/images/ch-02/figure-2-12.jpg "fig.2.12 Paths"

[fig-2-13]: http://networksciencebook.com/images/ch-02/figure-2-13.jpg "fig.2.13 Pathology"

[fig-2-14]: http://networksciencebook.com/images/ch-02/figure-2-14.jpg "fig.2.14 Applying the BFS Algorithm"

[02-09]: http://networksciencebook.com/chapter/2#connectedness "Connectedness"

[fig-2-15]: http://networksciencebook.com/images/ch-02/figure-2-15.jpg "fig.2.15 Connected and Disconnected Networks"