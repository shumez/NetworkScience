<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/NetworkScience/02
Author: 	shumez <https://github.com/shumez>
Created: 	2019-02-13 17:10:6
Modified: 	2019-06-03 16:37:58
-----
Copyright (c) 2019 shumez
-->

# [02. Graph Theory][02]

## Contents

* [02.01. The Bridges of Königsberg][0201]
* [02.02. Networks and Graphs][0202]
* [02.03. Degree, Average Degree and Degree Distribution][0203]
    * [02.03.01. Degree][020301]
    * [02.03.02. Average Degree][020302]
    * [02.03.03. Degree Distribution][020303]
* [02.04. Adjacency Matrix][0204]
* [02.05. Real Networks are Sparse][0205]
* [02.06. Weighted Networks][0206]
    * [02.06.01. Metcalfe Law: the Value of a Network][020601]
* [02.07. Bipartite Networks][0207]
* [02.08. Paths and Distances][0208]
    * [02.08.01. Shortest Path][020801]
    * [Box 02.04. Number of Shortest Paths Between Two Nodes][box0204]
    * [02.08.02. Network Diameter][020802]
    * [02.08.03. Average Path Length][020803]
    * [Box 02.05. Breadth-First Search Algorithm][box0205]
* [02.09. Connectedness][0209]
    * [Box 02.06. Finding the Connected Components of a Network][box0206]
* [02.10. Clustering Coefficient][0210]
* [02.11. Summary][0211]
* [02.12. Homework][0212]



## 02.01. The Bridges of Königsberg

[![fig-2-1][fig-2-1]][fig-2-1]

([Alexanderson, G., 2006])



## 02.02. Networks and Graphs

- $N$ *num of nodes*, *size* of the network
- \(L\) *num of links*, (2, 4)

[![fig-2-2][fig-2-2]][fig-2-2]

<!-- <iframe src="http://networksciencebook.com/images/ch-02/video-2-1.m4v"> -->

## 02.03. Degree, Average Degree and Degree Distribution

*degree*

### 02.03.01. Degree

\(k_i\): degree of \(i\)-th node 

\(k_1=2, k_2=3, k_3=2, k_4=1 \)

\[ L = \frac{1}{2} \sum_{i=1}^N k_i \tag{2.1} \]


### 02.03.02. Average Degree

undirected

\[ \langle k \rangle = \frac{1}{N} \sum_{i=1}^N k_j = \frac{2L}{N} \tag{2.2} \]

directed

- \(k_i^{in}\): incoming degree
- \(k_i^{out}\): outgoing degree

\[ k_i = k_i^{in} + k_i^{out} \tag{2.3} \]


\[ L = \sum_{i=1}^N k_i^{in} = \sum_{i=1}^N k_i^{out} \tag{2.4} \]


\[ \langle k^{in} \rangle = \frac{1}{N} \sum_{i=1}^N k_i^{in} = \langle k^{out} \rangle = \frac{1}{N} \sum_{i=1}^N k_i^{out} = \frac{L}{N} \tag{2.5} \]


### 02.03.03. Degree Distribution

\( p_k \): *degree distribution*, a randomly selected node in the network has degree \(k\)

\[ \sum_{k=1}^\infty p_k = 1 \tag{2.6} \]

\[ p_k = \frac{N_k}{N} \tag{2.7} \]

- \(N_k\): num of degree-k nodes

\[ \langle k \rangle = \sum_{k=0}^\infty kp_k \tag{2.8} \]


[![fig.2.3][fig-2-3]][fig-2-3]


[![fig.2.4][fig-2-4]][fig-2-4]



## 02.04. Adjacency Matrix

*adjacenct matrix*: \(N\) rows, \(N\) cols

\[ 
    A_{ij} = 
    \begin{cases} 
        1 &\text{there is a link} \\ 
        0 &\text{there is NOT} 
    \end{cases} 
\]


undirected

\[ k_i = \sum_{j=1}^N A_{ji} = \sum_{j=1}^N A_{ji} \tag{2.9} \]


directed

\[ k_i^{in} = \sum_{j=1}^N A_{ij}, \\ k_i^{out} = \sum_{j=1}^N A_{ji} \tag{2.10} \]


\[ 2L = \sum_{i=1}^N k_i^{in} = \sum_{i=1}^N k_i^{out} = \sum_{ij}^N A_{ij} \tag{2.11} \]

[![fig.2.5][fig-2-5]][fig-2-5]



## 02.05. Real Networks are Sparse

\[ L_{max} = \frac{N(N-1)}{2} \tag{2.12} \]

in a **complete graph** of size \(N\)

[![fig.2.6][fig-2-6]][fig-2-6]

real networks 

[![fig.2.7][fig-2-7]][fig-2-7]



## 02.06. Weighted Networks

\[ A_{ij} = w_{ij} \]


### 02.06.01. Metcalfe Law: the Value of a Network

**Metcalfe's law**:

val \(\propto N^2 \) 

([Gilder, G., 1993])

[![fig.2.8][fig-2-8]][fig-2-8]



## 02.07. Bipartite Networks


**bipartite graph** (**bigraph**) :

NO U-U / V-V links

[![fig.2.9][fig-2-9]][fig-2-9]


([Goh, K.I., 2007])

[![fig.2.10][fig-2-10]][fig-2-10]


[![fig.2.11][fig-2-11]][fig-2-11]



## 02.08. Paths and Distances


**path length**: num of links the path contains


[![fig.2.12][fig-2-12]][fig-2-12]


### 02.08.01. Shortest Path

**distance**: \(d_{ij}\) shortest path 

undirected, \( d_{ij} = d_{ji} \)

directed, \( d_{ij} \neq d_{ji} \)


[![fig.2.13][fig-2-13]][fig-2-13]

- shortest path (**Geodesic path** \(d\))
- **diamter** (\(d_{max}\)): longest shortest path in graph
- **average path length** (\(\langle d \rangle\))
- **cycle** 
- **Eulerian path**: transverse each link exactly once
- **Hamiltonian path**: visit each node exactly 


### Box 02.04. Number of Shortest Paths Between Two Nodes

- \(N_{ij}\) (num of shortest paths)
- \(d_{ij}\) (distance)
- \(A_{ij}\) (adjacency mat)


\(d_{ij} = 1\) if direct link, \(A_{ij} = 1\)

\(d_{ij} = 2 \) if path of length two, \(A_{ik}A_{kj} = 1\)

num of \(d_{ij}=2\) paths between \(i\) and \(j\) is 

\[ N_{ij}^{(2)} = \sum_{k=1}^N A_{ik}A_{jk} = A_{ij}^2 \]


\(d_{ij} = d\), \(A_{ik}\cdots A_{lj} = 1\)

\[ N_{ij}^{(d)} = A_{ij}^d \]


### 02.08.02. Network Diameter

**diameter** \(d_{max}\): max shortest path 

for larger networks, determined using the **BFS algorithm**


### 02.08.03. Average Path Length

**average path length** \(\langle d \rangle \)

\[ \langle d \rangle = \frac{1}{N(N-1)} \sum_{i,j = 1,N; \\i \neq j} \tag{2.14} \]


### Box 02.05. Breadth-First Search Algorithm

[![fig.2.14][fig-2-14]][fig-2-14]



## 02.09. Connectedness

**bridge**

[![fig.2.15][fig-2-15]][fig-2-15]


### Box 02.06. Finding the Connected Components of a Network



## 02.10. Clustering Coefficient

**clustering coefficient**

([Watts, D.J., Strogatz, S.H., 1998])

\[ C_i = \frac{2 L_i}{k_i (k_i - 1)} \tag{2.15} \]

\(L_i\): num of links between the \(k_i\) neighbors of node \(i\) 

\(C_i\) \([0, 1]\)

\[ C_i = 
    \begin{cases} 
        0  \\ 
        1 
    \end{cases} \]


[![fig.2.16][fig-2-16]][fig-2-16]


**average clustering coefficient** \( \langle C \rangle \)

\[ \langle C \rangle = \frac{1}{N} \sum_{i=1}^N C_i \tag{2.16} \]

([Barrat, A., 2004], [Onnela, J.P., 2005], [Zhang, B., 2005], [Holme, P., 2007])



## 02.11. Summary

[![fig.2.17][fig-2-17]][fig-2-17]

*Undirected*

*Self-loops*

*Multigraph / Simple Graphs*

*Directed*

*Wighted*

*Complete*


[![fig.2.18][fig-2-18]][fig-2-18]



## 02.12. Homework











##

[Network Science]: http://networksciencebook.com/ "Albert-László Barabási, Network Science"

[02]: http://networksciencebook.com/chapter/2 "Graph Theory"
[0201]: #0201_the_bridges_of_konigsberg
[0202]: #0202_networks_and_graphs
[0203]: #0203_degree_average_degree_and_degree_distribution
[020301]: #020301_degree
[020302]: #020302_average_degree
[020303]: #020303_degree_distribution
[0204]: #0204_adjacency_matrix
[0205]: #0205_real_networks_are_sparse
[0206]: #0206_weighted_networks
[020601]: #020601_metcalfe_law_the_value_of_a_network
[0207]: #0207_bipartite_networks
[0208]: #0208_paths_and_distances
[020801]: #020801_shortest_path
[box0204]: #box_0204_number_of_shortest_paths_between_two_nodes
[020802]: #020802_network_diameter
[020803]: #020803_average_path_length
[box0205]: #box_0205_breadth-first_search_algorithm
[0209]: #0209_connectedness
[box0206]: #box_0206_finding_the_connected_components_of_a_network
[0210]: #0210_clustering_coefficient
[0211]: #0211_summary
[0212]: #0212_homework

[02-01]: http://networksciencebook.com/chapter/2#bridges "The Bridges of Königsberg"
[02-02]: http://networksciencebook.com/chapter/2#networks-graphs "Networks and Graphs"
[02-03]: http://networksciencebook.com/chapter/2#degree "Degree, Average Degree and Degree Distribution"
[02-04]: http://networksciencebook.com/chapter/2#matrix "Adjacency Matrix"
[02-05]: http://networksciencebook.com/chapter/2#real-networks "Real Networks are Sparse"
[02-06]: http://networksciencebook.com/chapter/2#weighted-networks "Weighted Networks"
[02-07]: http://networksciencebook.com/chapter/2#bipartite-networks
[02-08]: http://networksciencebook.com/chapter/2#paths "Paths and Distances"
[02-09]: http://networksciencebook.com/chapter/2#connectedness "Connectedness"
[02-10]: http://networksciencebook.com/chapter/2#clustering "Clustering Coefficient"
[02-11]: http://networksciencebook.com/chapter/2#summary2 "Summary"
[02-12]: http://networksciencebook.com/chapter/2#homework2 "Homework"

<!-- fig -->
[fig-2-1]: http://networksciencebook.com/images/ch-02/figure-2-1.jpg "fig.2.1 The Bridges of Königsberg"
[fig-2-2]: http://networksciencebook.com/images/ch-02/figure-2-2.jpg "fig.2.2 Different Networks, Same Graph"
[fig-2-3]: http://networksciencebook.com/images/ch-02/figure-2-3.jpg "fig.2.3 Degree Distribution"
[fig-2-4]: http://networksciencebook.com/images/ch-02/figure-2-4.jpg "fig.2.4 Degree Distribution of a Real Network"
[fig-2-5]: http://networksciencebook.com/images/ch-02/figure-2-5.jpg "fig.2.5 The Adjacency Matrix"
[fig-2-6]: http://networksciencebook.com/images/ch-02/figure-2-6.jpg "fig.2.6 Complete Graph"
[fig-2-7]: http://networksciencebook.com/images/ch-02/figure-2-7.jpg "fig.2.7 The Adjacency Matrix is Sparse"
[fig-2-8]: http://networksciencebook.com/images/ch-02/figure-2-8.jpg "fig.2.8 Metcalfe’s Law"
[fig-2-9]: http://networksciencebook.com/images/ch-02/figure-2-9.jpg "fig.2.9 Bipartite Network"
[fig-2-10]: http://networksciencebook.com/images/ch-02/figure-2-10.jpg "fig.2.10 Human Disease Network"
[fig-2-11]: http://networksciencebook.com/images/ch-02/figure-2-11.jpg "fig.2.11 Tripartite Network"
[fig-2-12]: http://networksciencebook.com/images/ch-02/figure-2-12.jpg "fig.2.12 Paths"
[fig-2-13]: http://networksciencebook.com/images/ch-02/figure-2-13.jpg "fig.2.13 Pathology"
[fig-2-14]: http://networksciencebook.com/images/ch-02/figure-2-14.jpg "fig.2.14 Applying the BFS Algorithm"
[fig-2-15]: http://networksciencebook.com/images/ch-02/figure-2-15.jpg "fig.2.15 Connected and Disconnected Networks"
[fig-2-16]: http://networksciencebook.com/images/ch-02/figure-2-16.jpg "fig.2.16 Clustering Coefficient"
[fig-2-17]: http://networksciencebook.com/images/ch-02/figure-2-17.jpg "fig.2.17 Graphology "
[fig-2-18]: http://networksciencebook.com/images/ch-02/figure-2-18.jpg "Characterizing a Real Network"


<!-- ref -->
[Alexanderson, G., 2006]: https://www.ams.org/journals/bull/2006-43-04/S0273-0979-06-01130-X/S0273-0979-06-01130-X.pdf "Alexanderson, G., 2006. About the cover: Euler and Königsberg’s Bridges: A historical view. Bulletin of the american mathematical society, 43(4), pp.567-573."
[Gilder, G., 1993]: https://scholar.google.co.jp/scholar?hl=en&num=20&as_sdt=0%2C5&q=Gilder%2C+G.%2C+1993.+Metcalfe’s+law+and+legacy.+Forbes+ASAP%2C+13%2C+p.1993.&btnG= "Gilder, G., 1993. Metcalfe’s law and legacy. Forbes ASAP, 13, p.1993."
[Goh, K.I., 2007]: https://www.pnas.org/content/104/21/8685
[Watts, D.J., Strogatz, S.H., 1998]: http://leonidzhukov.net/hse/2014/socialnetworks/papers/watts-collective_dynamics-nature_1998.pdf "Watts, D.J. and Strogatz, S.H., 1998. Collective dynamics of ‘small-world’networks. nature, 393(6684), p.440."
[Barrat, A., 2004]: https://www.pnas.org/content/pnas/101/11/3747.full.pdf "Barrat, A., Barthelemy, M., Pastor-Satorras, R. and Vespignani, A., 2004. The architecture of complex weighted networks. Proceedings of the national academy of sciences, 101(11), pp.3747-3752."
[Onnela, J.P., 2005]: https://arxiv.org/pdf/cond-mat/0408629.pdf "Onnela, J.P., Saramäki, J., Kertész, J. and Kaski, K., 2005. Intensity and coherence of motifs in weighted complex networks. Physical Review E, 71(6), p.065103."
[Zhang, B., 2005]: http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.471.9599&rep=rep1&type=pdf "Zhang, B. and Horvath, S., 2005. A general framework for weighted gene co-expression network analysis. Statistical applications in genetics and molecular biology, 4(1)."
[Holme, P., 2007]: https://arxiv.org/pdf/cond-mat/0411634.pdf "Holme, P., Park, S.M., Kim, B.J. and Edling, C.R., 2007. Korean university life in a network perspective: Dynamics of a large affiliation network. Physica A: Statistical Mechanics and its Applications, 373, pp.821-830."

<style type="text/css">
	img{width: 51%; float: right;}
</style>