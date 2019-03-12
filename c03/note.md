<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c03
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-06 20:27:3
Modified: 	2019-03-12 14:33:29
-----
Copyright (c) 2019 shumez
-->

# 03 Random Networks

## Contents

01. [Introduction](#0301-Introduction)
02. [The Random Network Model](#0302-The-Random-Network-Model)
    * [Box 3-1 Defining Random Networks](#Box-3-1-Defining-Random-Networks)
    * [Box 3-2 Random Networks - a Brief History](#Box-3-2-Random-Networks---a-Brief-History)
03. [Number of Links](#0303-Number-of-Links)
    * [Box 3-3 Binomial Distribution - Mean and Variance](#Box-3-3-Binomial-Distribution---Mean-and-Variance)
04. [Degree Distribution](#0304-Degree-Distribution)
    * [Binomial Distribution](#Binomial-Distribution)
    * [Poisson Distribution](#Poisson-Distribution)


## 03.01 Introduction


## 03.02 The Random Network Model

### Box 3-1 Defining Random Networks

- \( G(N, L) \) model :
    - \(N\) labeled node are connedted with \(L\) randomly placed links
    - fixes the total num of links \(L\)
    - average degree of node \( \langle k \rangle = \frac{2L}{N} \)
- \( G(N, p) \) model :
    - \(N\) labeled nodes is connected with probability \(p\)
    - fixes prob \(p\)


### 

**random graph** (**random network**, **Erdős-Rényi network**)


### Box 3-2 Random Networks - a Brief History



## 03.03 Number of Links

- prob that \(L\) of attempts to connect \( \frac{N(N-1)}{2} \) pairs of nodes have result in link, is \(p^L\)
- prob that the remaining \( \frac{N(N-1)}{2} \) pairs of nodes have  not resulted in a link is
    \( (1 - p)^{\frac{N (N - 1)}{2} - L} \)
- conmbinational factor
    <!-- \[ \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} \tag{3.0} \] -->
    ![eq.3.0][eq_3_00]

<!-- \[ p_L = \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} p^L (1 - p)^{\frac{N (N - 1)}{2} - L} \tag{3.1} \] -->
![eq.3.1][eq_3_01]


expected num of links

<!-- \[ \langle L \rangle = \sum_{L=0}^{\frac{N(N-1)}{2}} LP_L = p \frac{N(N-1)}{2} \tag{3.2} \] -->
![eq.3.2][eq_3_02]

<!-- \( L_{max} = \frac{N(N-1)}{2} \) -->
<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;L_{max}&space;=&space;\frac{N(N-1)}{2}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;L_{max}&space;=&space;\frac{N(N-1)}{2}" title="L_{max} = \frac{N(N-1)}{2}" /></a>

<!-- \[ \langle k \rangle = \frac{2 \langle L \rangle}{N} = p (N - 1) \tag{3.3} \] -->
![eq.3.3][eq_3_03]

[![fig.3.3][fig_03_03]][fig_03_03]
\(p=\frac{1}{6}\), \(N=12\), \(L=10, 18, 8\)

\( p = .03\), \( N = 100 \)


### Box 3-3 Binomial Distribution - Mean and Variance

\[ p_x = \begin{pmatrix}N \\ x\end{pmatrix} p^x (1-p)^{N-x} \]

<!-- \[ \langle x \rangle = \sum_{x=0}^N xp_x = Np \tag{3.4} \] -->
![eq.3.4][eq_3_04]

<!-- \[ \langle x^2 \rangle = \sum_{x=0}^N x^2 p_x = p(1-p)N + p^2 N^2 \tag{3.5} \] -->
![eq.3.5][eq_3_05]

standard deviation

<!-- \[ \sigma_x = \big( \langle x^2 \rangle - \langle x \rangle^2 \big)^{\frac{1}{2}} = [ p(1 - p) N ]^{\frac{1}{2}} \tag{3.6} \] -->
![eq.3.6][eq_3_06]


## 03.04 Degree Distribution

degree dist \(p_k\), degree \(k\)


|         | Binominal | Poisson |
|---------|:---------:|:--------|
| degree dist \(p_k\) | \( \begin{pmatrix}N-1 \\ k\end{pmatrix} p_k (1-p)^{N-1-k} \) | \( e^{-\langle k \rangle} \frac{\langle k \rangle}{k!} \) |
| peak at \(k\) | \( \langle k \rangle = p(N-1) \) | \( \langle k \rangle \) |
| width \( \sigma_k \) | \( p(1-p)(N-1) \) | \( \langle k \rangle^{\frac{1}{2}} \) |



[![fig.3.4][fig_03_04]][fig_03_04]


### Binomial Distribution

node <!--\(i\)--><img src="https://latex.codecogs.com/gif.latex?\inline&space;i"> has <!--\(k\)--><img src="https://latex.codecogs.com/gif.latex?\inline&space;k">

- prob that \(k\) of its links are present / \(p^k\) 
- prob that remaining \( (N-1-k) \) links are missing / \((1-p)^{N-1-k}\)
- 

<!-- \[ \begin{pmatrix} N-1 \\ k \end{pmatrix} \] -->
<img src="https://latex.codecogs.com/gif.latex?\begin{pmatrix}N-1\\k\end{pmatrix}">


<!-- \[ p_k = \begin{pmatrix}N-1\\k\end{pmatrix} p^k (1-p)^{N-1-k} \tag{3.7} \] -->
![eq.3.7][eq_3_07]


### Poisson Distribution

<!-- \[ p_k = e^{- \langle k \rangle } \frac{\langle k \rangle^k}{k!} \tag{3.8} \] -->
![eq.3.8][eq_3_08]


*degree distributioin of a random network*




## 






[eq_3_00]: https://latex.codecogs.com/gif.latex?\begin{pmatrix}\frac{N(N-1)}{2}\\L\end{pmatrix} "eq.3.0"
[eq_3_01]: https://latex.codecogs.com/gif.latex?p_L=\begin{pmatrix}\frac{N(N-1)}{2}\\L\end{pmatrix}p^L(1-p)^{\frac{N(N-1)}{2}-L} "eq.3.1"
[eq_3_02]: https://latex.codecogs.com/gif.latex?\langle&space;L\rangle=\sum_{L=0}^{\frac{N(N-1)}{2}}LP_L=p\frac{N(N-1)}{2} "eq.3.2"
[eq_3_03]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1) "eq.3.3"
[fig_03_03]: http://networksciencebook.com/images/ch-03/figure-3-3.jpg "Fig.3.3 Random Networks are Truly Random"
[eq_3_04]: https://latex.codecogs.com/gif.latex?\langle&space;x\rangle=\sum_{x=0}^Nxp_x=Np
[eq_3_05]: https://latex.codecogs.com/gif.latex?\langle&space;x^2\rangle=\sum_{x=0}^Nx^2p_x=p(1-p)N+p^2&space;N^2
[eq_3_06]: https://latex.codecogs.com/gif.latex?\sigma_x=\big(\langle&space;x^2\rangle-\langle&space;x\rangle^2\big)^{\frac{1}{2}}=[p(1-p)N]^{\frac{1}{2}}
[fig_03_04]: http://networksciencebook.com/images/ch-03/figure-3-4.jpg "Fig.3.4 Binomial vs. Poisson Degree Distribution"
[eq_3_07]: https://latex.codecogs.com/gif.latex?p_k=\begin{pmatrix}N-1\\k\end{pmatrix}p^k(1-p)^{N-1-k}
[eq_3_08]: https://latex.codecogs.com/gif.latex?p_k=e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle^k}{k!}

<!-- 
https://latex.codecogs.com/gif.latex?\inline&space;"
https://latex.codecogs.com/gif.latex?"
-->

<style type="text/css">
	/* img{width: 50%; float: right;} */
</style>