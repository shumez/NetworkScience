<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c02
Author: 	shumez <https://github.com/shumez>
Created: 	2019-02-13 17:10:6
Modified: 	2019-02-13 17:10:18
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

\( L = \frac{1}{2} \sum_{i=1}^N k_i \) (2.1)


### Average Degree

undirected

\( \langle k \rangle = \frac{1}{N} \sum_{i=1}^N k_j = \frac{2L}{N} \) (2.2)

directed

- \(k_i^{in}\): incoming degree
- \(k_i^{out}\): outgoing degree

\( k_i = k_i^{in} + k_i^{out} \) (2.3)


\( L = \sum_{i=1}^N k_i^{in} = \sum_{i=1}^N k_i^{out} \) (2.4)


\( \langle k^{in} \rangle = \frac{1}{N} \sum_{i=1}^N k_i^{in} = \langle k^{out} \rangle = \frac{1}{N} \sum_{i=1}^N k_i^{out} = \frac{L}{N} \) (2.5)


### Degree Distribution

\( p_k \): *degree distribution*, a randomly selected node in the network has degree \(k\)

\( \sum_{k=1}^\infty p_k = 1 \) (2.6)

\( p_k = \frac{N_k}{N} \) (2.7)

- \(N_k\): num of degree-k nodes

\( \langle k \rangle = \sum_{k=0}^\infty kp_k \) (2.8)


[![fig.2.3][fig-2-3]][fig-2-3]


[![fig.2.4][fig-2-4]][fig-2-4]



## [02-04] Adjacency Matrix

*adjacenct matrix*: N rows, N cols

\( A_{ij} = \begin{cases} 1 &\text{there is a link} \\ 0 &\text{there is not} \end{cases} \) 


undirected

\( k_i = \sum_{j=1}^N A_{ji} = \sum_{j=1}^N A_{ji} \) (2.9)


directed

\( k_i^{in} = \sum_{j=1}^N A_{ij}, \\ k_i^{out} = \sum_{j=1}^N A_{ji} \)
(2.10)


\( 2L = \sum_{i=1}^N k_i^{in} = \sum_{i=1}^N k_i^{out} = \sum_{ij}^N A_{ij} \) (2.11)

[![fig.2.5][fig-2-5]][fig-2-5]



## [02-05] Real Networks are Sparse

\( L_{max} = \frac{N(N-1)}{2} \) (2.12)

in a *complete graph* of size \(N\)

[![fig.2.6][fig-2-6]][fig-2-6]

real networks 

[![fig.2.7][fig-2-7]][fig-2-7]





[Network Science]: http://networksciencebook.com/ "Albert-László Barabási, Network Science"

[02]: http://networksciencebook.com/chapter/2 "Graph Theory"

[02-01]: http://networksciencebook.com/chapter/2#bridges "The Bridges of Königsberg"

[fig-2-1]: http://networksciencebook.com/images/ch-02/figure-2-1.jpg "The Bridges of Königsberg"

[Alexanderson, G., 2006]: https://www.ams.org/journals/bull/2006-43-04/S0273-0979-06-01130-X/S0273-0979-06-01130-X.pdf "Alexanderson, G., 2006. About the cover: Euler and Königsberg’s Bridges: A historical view. Bulletin of the american mathematical society, 43(4), pp.567-573."


[02-02]: http://networksciencebook.com/chapter/2#networks-graphs "Networks and Graphs"

[fig-2-2]: http://networksciencebook.com/images/ch-02/figure-2-2.jpg "Different Networks, Same Graph"

[02-03]: http://networksciencebook.com/chapter/2#degree "Degree, Average Degree and Degree Distribution"

[fig-2-3]: http://networksciencebook.com/images/ch-02/figure-2-3.jpg "Degree Distribution"

[fig-2-4]: http://networksciencebook.com/images/ch-02/figure-2-4.jpg "Degree Distribution of a Real Network "

[02-04]: http://networksciencebook.com/chapter/2#matrix "Adjacency Matrix"

[fig-2-5]: http://networksciencebook.com/images/ch-02/figure-2-5.jpg


[02-05]: http://networksciencebook.com/chapter/2#real-networks "Real Networks are Sparse"

[fig-2-6]: http://networksciencebook.com/images/ch-02/figure-2-6.jpg "Complete Graph"

[fig-2-7]: http://networksciencebook.com/images/ch-02/figure-2-7.jpg "The Adjacency Matrix is Sparse"