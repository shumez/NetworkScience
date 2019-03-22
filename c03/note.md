<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c03
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-06 20:27:3
Modified: 	2019-03-22 15:43:38
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
05. [Real Networks are Not Poisson](#0305-Real-Networks-are-Not-Poisson)
    * [Box 3-4 Why are Hubs Missing?](#Box-3-4-Why-are-Hubs-Missing?)


## 03.01 Introduction


## 03.02 The Random Network Model

![][N] nodes, connected w/ probability ![][p] 

### Box 3-1 Defining Random Networks

- ![][G(N,L)] model :
    - ![][N] labeled node are connedted with ![][L] randomly placed links
    - fixes the total num of links ![][L]
    - average degree of node ![][\langle&space;k\rangle=\frac{2L}{N}]
- ![][G(N,p)] model :
    - ![][N] labeled nodes is connected with probability ![][p]
    - fixes prob ![][p]


### 

**random graph** (**random network**, **Erdős-Rényi network**)


### Box 3-2 Random Networks - a Brief History

- Anatol Rapoport
- *Random graph theory* Pál Erdős and Alfréd Rényi
- Edgar Nelson Gilbert 


## 03.03 Number of Links

- prob that ![][L] of attempts to connect ![][\frac{N(N-1)}{2}] pairs of nodes have result in link, is ![][p^L]
- prob that the remaining ![][\frac{N(N-1)}{2}] pairs of nodes have  not resulted in a link is
    ![(1-p)^{\frac{N(N-1)}{2}-L}][(1-p)^{\frac{N(N-1)}{2}-L}]
- conmbinational factor
    <!-- \[ \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} \tag{3.0} \] -->
    ![eq.3.0][eq_03_00]

<!-- \[ p_L = \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} p^L (1 - p)^{\frac{N (N - 1)}{2} - L} \tag{3.1} \] -->
![eq.3.1][p_L=\begin{pmatrix}\frac{N(N-1)}{2}\\L\end{pmatrix}p^L(1-p)^{\frac{N(N-1)}{2}-L}]


expected num of links

<!-- \[ \langle L \rangle = \sum_{L=0}^{\frac{N(N-1)}{2}} LP_L = p \frac{N(N-1)}{2} \tag{3.2} \] -->
![eq.3.2][\langle&space;L\rangle=\sum_{L=0}^{\frac{N(N-1)}{2}}LP_L=p\frac{N(N-1)}{2}]

<!-- \( L_{max} = \frac{N(N-1)}{2} \) -->
![][L_{max}=\frac{N(N-1)}{2}]


<!-- \[ \langle k \rangle = \frac{2 \langle L \rangle}{N} = p (N - 1) \tag{3.3} \] -->
![eq.3.3][\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1)]

from ![][\langle&space;k\rangle=0] to ![][\langle&space;k\rangle=N-1]

[![fig.3.3][fig_03_03]][fig_03_03]
![][p=\frac{1}{6}], ![][N=12], ![][L=10,&space;18,&space;8]

![][p=.03], ![][N=100]


### Box 3-3 Binomial Distribution - Mean and Variance

<!-- \[ p_x = \begin{pmatrix}N \\ x\end{pmatrix} p^x (1-p)^{N-x} \] -->
![][p_x=\begin{pmatrix}N\\x\end{pmatrix}p^x(1-p)^{N-x}]

<!-- \[ \langle x \rangle = \sum_{x=0}^N xp_x = Np \tag{3.4} \] -->
![eq.3.4][\langle&space;x\rangle=\sum_{x=0}^Nxp_x=Np]

<!-- \[ \langle x^2 \rangle = \sum_{x=0}^N x^2 p_x = p(1-p)N + p^2 N^2 \tag{3.5} \] -->
![eq.3.5][\langle&space;x^2\rangle=\sum_{x=0}^Nx^2p_x=p(1-p)N+p^2&space;N^2]

standard deviation

<!-- \[ \sigma_x = \big( \langle x^2 \rangle - \langle x \rangle^2 \big)^{\frac{1}{2}} = [ p(1 - p) N ]^{\frac{1}{2}} \tag{3.6} \] -->
![eq.3.6][\sigma_x=\big(\langle&space;x^2\rangle-\langle&space;x\rangle^2\big)^{\frac{1}{2}}=\Big(p(1-p)N\Big)^{\frac{1}{2}}]


## 03.04 Degree Distribution

degree dist ![][p_k], degree ![][k]


|               |               | Binominal                                                 | Poisson |
|--------------:|:-------------:|:---------------------------------------------------------:|:------------------------------------------:|
| degree dist   | ![][p_k]      | ![][\begin{pmatrix}N-1\\k\end{pmatrix}p_k(1-p)^{N-1-k}]   | ![][e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle}{k!}] |
| peak at       | ![][k]        | ![][\langle&space;k\rangle=p(N-1)]                        | ![][\langle&space;k\rangle]               |
| width         | ![][\sigma_k] | ![][p(1-p)(N-1)]                                          | ![][\langle&space;k\rangle^{\frac{1}{2}}] |



[![fig.3.4][fig_03_04]][fig_03_04]


### Binomial Distribution

prob that node ![][i] has ![][k] links is product of 3 terms:

1. prob that ![][k] of its links are present / ![][p^k]
2. prob that remaining (![][N-1-k]) links are missing / ![][(1-p)^{N-1-k}]
3. ![][\begin{pmatrix}N-1\\k\end{pmatrix}]
<!-- \[ \begin{pmatrix} N-1 \\ k \end{pmatrix} \] -->

<!-- \[ p_k = \begin{pmatrix}N-1\\k\end{pmatrix} p^k (1-p)^{N-1-k} \tag{3.7} \] -->
![eq.3.7][p_k=\begin{pmatrix}N-1\\k\end{pmatrix}p^k(1-p)^{N-1-k}]

average degree ![][\langle&space;k\rangle]
second moment ![][\langle&space;k^2\rangle] & variance ![][\sigma_k]


### Poisson Distribution

sparse networks: ![][\langle&space;k\rangle\ll&space;N]

eq.3.7 is approx'd by Poisson dist

<!-- \[ p_k = e^{- \langle k \rangle } \frac{\langle k \rangle^k}{k!} \tag{3.8} \] -->
![eq.3.8][p_k=e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle^k}{k!}]

**degree distributioin of a random network**

[![fig.3.5][fig_03_05]][fig_03_05]
> The degree distribution of a random network with ‹k› = 50 and N = 102, 103, 104.
> Small Networks: Binomial
> For a small network (N = 102) the degree distribution deviates significantly from the Poisson form (3.8), as the condition for the Poisson approximation, N»‹k›, is not satisfied. Hence for small networks one needs to use the exact binomial form (3.7) (green line).

> Large Networks: Poisson
> For larger networks (N = 103, 104) the degree distribution becomes indistinguishable from the Poisson prediction (3.8), shown as a continuous grey line. Therefore for large N the degree distribution is independent of the network size. In the figure we averaged over 1,000 independently generated random networks to decrease the noise.


## 03.05 Real Networks are Not Poisson

social network
![][\langle&space;k\rangle\approx1000], ![][N\approx&space;7\times10^9] of individuals

![][k_{\text{max}}=1185] accuaitances

![][k_{\text{min}}=816]

despersion of random network is ![][\sigma_k=\langle&space;k\rangle^{\frac{1}{2}}], 
for ![][\langle&space;k\rangle=1000] ![][\sigma_k=31.62]
![][\langle&space;k\rangle\pm\sigma_k] range 


### Box 3-4 Why are Hubs Missing?

![][\frac{1}{k!}]

the Stirling approx

![][k!\sim\sqrt{2\pi&space;k}\bigg(\frac{k}{e}\bigg)^k]

![eq.3.9][p_k=\frac{e^{-\langle&space;k\rangle}}{\sqrt{2\pi&space;k}}\bigg(\frac{e\langle&space;k\rangle}{k}\bigg)^k]

![][k>e\langle&space;k\rangle]


### 

[![figure.3.6][fig_03_06]][fig_03_06]



## 


<!-- eq -->

<!-- 03.02 -->
<!-- Box 3-1 -->
[G(N,L)]: https://latex.codecogs.com/gif.latex?G(N,L)
[N]: https://latex.codecogs.com/gif.latex?N
[L]: https://latex.codecogs.com/gif.latex?L
[\langle&space;k\rangle=\frac{2L}{N}]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=\frac{2L}{N}
[G(N,p)]: https://latex.codecogs.com/gif.latex?G(N,p)
[p]: https://latex.codecogs.com/gif.latex?p

[\frac{N(N-1)}{2}]: https://latex.codecogs.com/gif.latex?\frac{N(N-1)}{2}
[p^L]: https://latex.codecogs.com/gif.latex?p^L
[\frac{N(N-1)}{2}]: https://latex.codecogs.com/gif.latex?\frac{N(N-1)}{2}
[(1-p)^{\frac{N(N-1)}{2}-L}]: https://latex.codecogs.com/gif.latex?(1-p)^{\frac{N(N-1)}{2}-L}
[eq_03_00]: https://latex.codecogs.com/gif.latex?\begin{pmatrix}\frac{N(N-1)}{2}\\L\end{pmatrix} "eq.3.0"
[p_L=\begin{pmatrix}\frac{N(N-1)}{2}\\L\end{pmatrix}p^L(1-p)^{\frac{N(N-1)}{2}-L}]: https://latex.codecogs.com/gif.latex?p_L=\begin{pmatrix}\frac{N(N-1)}{2}\\L\end{pmatrix}p^L(1-p)^{\frac{N(N-1)}{2}-L} "eq.3.1"
[\langle&space;L\rangle=\sum_{L=0}^{\frac{N(N-1)}{2}}LP_L=p\frac{N(N-1)}{2}]: https://latex.codecogs.com/gif.latex?\langle&space;L\rangle=\sum_{L=0}^{\frac{N(N-1)}{2}}LP_L=p\frac{N(N-1)}{2} "eq.3.2"
[L_{max}=\frac{N(N-1)}{2}]: https://latex.codecogs.com/gif.latex?L_{max}=\frac{N(N-1)}{2}
[\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1)]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1) "eq.3.3"
[\langle&space;k\rangle=0]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=0
[\langle&space;k\rangle=N-1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=N-1
[fig_03_03]: http://networksciencebook.com/images/ch-03/figure-3-3.jpg "Fig.3.3 Random Networks are Truly Random"
[p=\frac{1}{6}]: https://latex.codecogs.com/gif.latex?p=\frac{1}{6}
[N=12]: https://latex.codecogs.com/gif.latex?N=12
[L=10,&space;18,&space;8]: https://latex.codecogs.com/gif.latex?L=10,&space;18,&space;8
[p=.03]: https://latex.codecogs.com/gif.latex?p=.03
[N=100]: https://latex.codecogs.com/gif.latex?N=100
[p_x=\begin{pmatrix}N\\x\end{pmatrix}p^x(1-p)^{N-x}]: https://latex.codecogs.com/gif.latex?p_x=\begin{pmatrix}N\\x\end{pmatrix}p^x(1-p)^{N-x}
[\langle&space;x\rangle=\sum_{x=0}^Nxp_x=Np]: https://latex.codecogs.com/gif.latex?\langle&space;x\rangle=\sum_{x=0}^Nxp_x=Np "eq.3.4"
[\langle&space;x^2\rangle=\sum_{x=0}^Nx^2p_x=p(1-p)N+p^2&space;N^2]: https://latex.codecogs.com/gif.latex?\langle&space;x^2\rangle=\sum_{x=0}^Nx^2p_x=p(1-p)N+p^2&space;N^2 "eq.3.5"
[\sigma_x=\big(\langle&space;x^2\rangle-\langle&space;x\rangle^2\big)^{\frac{1}{2}}=\Big(p(1-p)N\Big)^{\frac{1}{2}}]: https://latex.codecogs.com/gif.latex?\sigma_x=\big(\langle&space;x^2\rangle-\langle&space;x\rangle^2\big)^{\frac{1}{2}}=\Big(p(1-p)N\Big)^{\frac{1}{2}} "eq.3.6"
[p_k]: https://latex.codecogs.com/gif.latex?p_k
[k]: https://latex.codecogs.com/gif.latex?k
[\begin{pmatrix}N-1\\k\end{pmatrix}p_k(1-p)^{N-1-k}]: https://latex.codecogs.com/gif.latex?\begin{pmatrix}N-1\\k\end{pmatrix}p_k(1-p)^{N-1-k}
[e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle}{k!}]: https://latex.codecogs.com/gif.latex?e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle}{k!}
[\langle&space;k\rangle=p(N-1)]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=p(N-1)
[\langle&space;k\rangle]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle
[\sigma_k]: https://latex.codecogs.com/gif.latex?\sigma_k
[p(1-p)(N-1)]: https://latex.codecogs.com/gif.latex?p(1-p)(N-1)
[\langle&space;k\rangle^{\frac{1}{2}}]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle^{\frac{1}{2}}
[fig_03_04]: http://networksciencebook.com/images/ch-03/figure-3-4.jpg "Fig.3.4 Binomial vs. Poisson Degree Distribution"
[i]: https://latex.codecogs.com/gif.latex?i
[p^k]: https://latex.codecogs.com/gif.latex?p^k
[N-1-k]: https://latex.codecogs.com/gif.latex?N-1-k
[(1-p)^{N-1-k}]: https://latex.codecogs.com/gif.latex?(1-p)^{N-1-k}
[\begin{pmatrix}N-1\\k\end{pmatrix}]: https://latex.codecogs.com/gif.latex?\begin{pmatrix}N-1\\k\end{pmatrix}
[p_k=\begin{pmatrix}N-1\\k\end{pmatrix}p^k(1-p)^{N-1-k}]: https://latex.codecogs.com/gif.latex?p_k=\begin{pmatrix}N-1\\k\end{pmatrix}p^k(1-p)^{N-1-k} "eq.3.7"
[\langle&space;k^2\rangle]: https://latex.codecogs.com/gif.latex?\langle&space;k^2\rangle
<!-- #Poisson-Distribution -->
[\langle&space;k\rangle\ll&space;N]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle\ll&space;N
[p_k=e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle^k}{k!}]: https://latex.codecogs.com/gif.latex?p_k=e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle^k}{k!} "eq.3.8"
[fig_03_05]: http://networksciencebook.com/images/ch-03/figure-3-5.jpg "Fig.3.5 Degree Distribution is Independent of the Network Size "
[\langle&space;k\rangle\approx1000]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle\approx1000
[N\approx&space;7\times10^9]: https://latex.codecogs.com/gif.latex?N\approx&space;7\times10^9
[k_{\text{max}}=1185]: https://latex.codecogs.com/gif.latex?k_{\text{max}}=1185
[k_{\text{min}}=816]: https://latex.codecogs.com/gif.latex?k_{\text{min}}=816
[\sigma_k=\langle&space;k\rangle^{\frac{1}{2}}]: https://latex.codecogs.com/gif.latex?\sigma_k=\langle&space;k\rangle^{\frac{1}{2}}
[\langle&space;k\rangle=1000]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=1000
[\sigma_k=31.62]: https://latex.codecogs.com/gif.latex?\sigma_k=31.62
[\langle&space;k\rangle\pm\sigma_k]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle\pm\sigma_k
[\frac{1}{k!}]: https://latex.codecogs.com/gif.latex?\frac{1}{k!}
[k!\sim\sqrt{2\pi&space;k}\bigg(\frac{k}{e}\bigg)^k]: https://latex.codecogs.com/gif.latex?k!\sim\sqrt{2\pi&space;k}\bigg(\frac{k}{e}\bigg)^k
[p_k=\frac{e^{-\langle&space;k\rangle}}{\sqrt{2\pi&space;k}}\bigg(\frac{e\langle&space;k\rangle}{k}\bigg)^k]: https://latex.codecogs.com/gif.latex?p_k=\frac{e^{-\langle&space;k\rangle}}{\sqrt{2\pi&space;k}}\bigg(\frac{e\langle&space;k\rangle}{k}\bigg)^k "eq.3.9"
[k>e\langle&space;k\rangle]: https://latex.codecogs.com/gif.latex?k>e\langle&space;k\rangle "\(k>e\langle&space;k\rangle\)"
[fig_03_06]: http://networksciencebook.com/images/ch-03/figure-3-6.jpg "Fig.3.6 Degree Distribution of Real Networks "


<!-- 
https://latex.codecogs.com/gif.latex?\inline&space;
https://latex.codecogs.com/gif.latex?
-->

<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->