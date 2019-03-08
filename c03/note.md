<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c03
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-06 20:27:3
Modified: 	2019-03-08 18:54:13
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
    \[ \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} \tag{3.0} \]

\[ p_L = \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} p^L (1 - p)^{\frac{N (N - 1)}{2} - L} \tag{3.1} \]


expected num of links

\[ \langle L \rangle = \sum_{L=0}^{\frac{N(N-1)}{2}} LP_L = p \frac{N(N-1)}{2} \tag{3.2} \]

\( L_{max} = \frac{N(N-1)}{2} \)

\[ \langle k \rangle = \frac{2 \langle L \rangle}{N} = p (N - 1) \tag{3.3} \]

[![fig.3.3][fig_03_03]][fig_03_03]
\(p=\frac{1}{6}\), \(N=12\), \(L=10, 18, 8\)

\( p = .03\), \( N = 100 \)


### Box 3-3 Binomial Distribution - Mean and Variance

\[ p_x = \begin{pmatrix}N \\ x\end{pmatrix} p^x (1-p)^{N-x} \]

\[ \langle x \rangle = \sum_{x=0}^N xp_x = Np \tag{3.4} \]

\[ \langle x^2 \rangle = \sum_{x=0}^N x^2 p_x = p(1-p)N + p^2 N^2 \tag{3.5} \]

standard deviation

\[ \sigma_x = \big( \langle x^2 \rangle - \langle x \rangle^2 \big)^{\frac{1}{2}} = [ p(1 - p) N ]^{\frac{1}{2}} \tag{3.6} \]





[fig_03_03]: http://networksciencebook.com/images/ch-03/figure-3-3.jpg "Random Networks are Truly Random"

<style type="text/css">
	img{width: 50%; float: right;}
</style>