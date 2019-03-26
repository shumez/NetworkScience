<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c03
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-06 20:27:3
Modified: 	2019-03-26 14:30:40
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
06. [The Evolution of a Random Network](#0306-The-Evolution-of-a-Random-Network)
    * [Box 3-5 Network Evolution in Graph Theory](#Box-3-5-Network-Evolution-in-Graph-Theory)
07. [Real Networks are Supercritical](#0307-Real-Networks-are-Supercritical)
08. [Small Worlds](#0308-Small-Worlds)
- 16. [Advanced Topic 3.E Fully Connected Regime](#0316-Advanced-Topic-3E-Fully-Connected-Regime)


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
    <!-- \[ \binom{\frac{N(N-1)}{2}}{L} \tag{3.0} \] -->
    ![eq.3.0][\binom{\frac{N(N-1)}{2}}{L}]

<!-- \[ p_L = \binom{\frac{N(N-1)}{2}}{L} p^L (1 - p)^{\frac{N (N - 1)}{2} - L} \tag{3.1} \] -->
![eq.3.1][p_L=\binom{\frac{N(N-1)}{2}}{L}p^L(1-p)^{\frac{N(N-1)}{2}-L}]


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

<!-- \[ p_x = \binom{N}{x} p^x (1-p)^{N-x} \] -->
![][p_x=\binom{N}{x}p^x(1-p)^{N-x}]

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
| degree dist   | ![][p_k]      | ![][\binom{N-1}{k}p_k(1-p)^{N-1-k}]   | ![][e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle}{k!}] |
| peak at       | ![][k]        | ![][\langle&space;k\rangle=p(N-1)]                        | ![][\langle&space;k\rangle]               |
| width         | ![][\sigma_k] | ![][p(1-p)(N-1)]                                          | ![][\langle&space;k\rangle^{\frac{1}{2}}] |



[![fig.3.4][fig_03_04]][fig_03_04]


### Binomial Distribution

prob that node ![][i] has ![][k] links is product of 3 terms:

1. prob that ![][k] of its links are present / ![][p^k]
2. prob that remaining (![][N-1-k]) links are missing / ![][(1-p)^{N-1-k}]
3. ![][\binom{N-1}{k}]
<!-- \[ \binom{N-1}{k} \] -->

<!-- \[ p_k = \binom{N-1}{k} p^k (1-p)^{N-1-k} \tag{3.7} \] -->
![eq.3.7][p_k=\binom{N-1}{k}p^k(1-p)^{N-1-k}]

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

*in a large random network the degree of most nodes is in the narrow vicinity of* ![][\langle&space;k\rangle]


### Box 3-4 Why are Hubs Missing?

![][\frac{1}{k!}]

the Stirling approx

![][k!\sim\sqrt{2\pi&space;k}\bigg(\frac{k}{e}\bigg)^k]

rewrite eq.3.8  as:

![eq.3.9][p_k=\frac{e^{-\langle&space;k\rangle}}{\sqrt{2\pi&space;k}}\bigg(\frac{e\langle&space;k\rangle}{k}\bigg)^k]

![][k>e\langle&space;k\rangle]


### 

[![figure.3.6][fig_03_06]][fig_03_06]


## 03.06 The Evolution of a Random Network

the size of the largest conneted cluster w/i the network, ![][N_G] varies w/ ![][\langle&space;k\rangle]

- for ![][p=0] we have ![][\langle&space;k\rangle=0], &there4; ![][N_G=1] and ![][\frac{N_G}{N}\rightarrow0] for large ![][N]
- for ![][p=1] we have ![][\langle&space;k\rangle=N-1], complete graph, &there4; ![][N_G=N] and ![][\frac{N_G}{N}=1]

<!-- ![video.3.2][video_03_02] -->

<iframe width="560" height="315" src="http://networksciencebook.com/images/ch-03/video-3-2.m4v" id="video_03_02" allowfullscreen></iframe>

grow from ![][N_G=1] to ![][N_G=N] if ![][\langle&space;k\rangle] increase from ![][0] to ![][N-1]


[Erdős P., Rényi A., 1960][1960RényiA_ErdősP] condition for teh emergence of the giant component is ([Erdős P., Rényi A., 1960][1960RényiA_ErdősP]):

![eq.3.10][\langle&space;k\rangle=1]

express eq.3.10 in terms of ![][p] using eq.3.3 ![eq.3.3][\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1)]

![eq.3.11][p_c=\frac{1}{N-1}\approx\frac{1}{N}]

the larger network, the smaller ![][p] is sufficient for the giant component

4 regimes: 

**Subcritical regime**: ![][0<\langle&space;k\rangle<1] (![][p<\frac{1}{N}])

for ![][\langle&space;k\rangle<1], 
![][N_G\sim\ln{N}]

&there4; ![][\frac{N_G}{N}\simeq\frac{\ln{N}}{N}\rightarrow0], ![][N\rightarrow\infty]


**Critical point**: ![][\langle&space;k\rangle=1] (![][p=\frac{1}{N}])

size of the largest component is
![][N_G\sim&space;N^{\frac{2}{3}}]

![][\frac{N_G}{N}\sim&space;N^{-\frac{1}{3}}] in the ![][N\rightarrow\infty] limit

e.g., ![][N=7\times10^9] nodes

for ![][\langle&space;k\rangle<1], 
![][N_G\simeq\ln{N}=\ln{(7\times10^9)}\simeq22.7]

for ![][\langle&space;k\rangle=1], 
![][N_G\sim&space;N^{\frac{2}{3}}=(7\times10^9)^{\frac{2}{3}}\simeq3\times10^6]


![fig.3.7][fig_03_07]


**Supercritical Regime**: ![][\langle&space;k\rangle>1] (![][p>\frac{1}{N}])

![eq.3.12][\frac{N_G}{N}\sim\langle&space;k\rangle-1]

or

![eq.3.13][N_G\sim(p-p_c)N]

where ![][p_c] is given by eq.3.11 (![eq.3.11][p_c=\frac{1}{N-1}\approx\frac{1}{N}])


**Connected Regime**: ![][\langle&space;k\rangle>\ln{N}] (![][p>\frac{\ln{N}}{N}])

![][N_G\simeq&space;N]

![eq.3.14][\langle&space;k\rangle=\ln{N}]

![][\frac{\ln{N}}{N}\rightarrow0] for large ![][N]


### Box 3-5 Network Evolution in Graph Theory

![][p(N)] scales as ![][N^z] where ![][z] is tunable param ![][-\infty,0]

![fig.3.8][fig_03_08]


## 03.07 Real Networks are Supercritical


- ![][\langle&space;k\rangle=1] 
- ![][\langle&space;k\rangle>\ln{N}]

Network	                | ![][N]	| ![][L]	    | ![][\langle&space;K\rangle]| ![][\ln{N}]   |
------------------------|----------:|--------------:|------:|------:|
Internet	            | 192,244	| 609,066	    | 6.34	| 12.17 |
Power Grid	            | 4,941	    | 6,594	        | 2.67	| 8.51  |
Science Collaboration	| 23,133	| 94,437	    | 8.08	| 10.05 |
Actor Network	        | 702,388	| 29,397,908	| 83.71	| 13.46 |
Protein Interactions	| 2,018	    | 2,930	        | 2.90	| 7.61  |


most real networks are in the supercritical regime

giant component coexist w/ many disconnected components

[![Fig.3.9][fig_03_09]][fig_03_09]


## 03.08 Small Worlds

**small world phenomenon** aka, **six degrees of separation**

[![fig.3.10][fig_03_10]][fig_03_10]

*the distance between two randomly chosen nodes in a network is short*

2 questions:
- short mean
- existenxe of these shord distances


- ![][\langle&space;k\rangle] nodes at distance ![][d=1]
- ![][\langle&space;k\rangle^2] nodes at distance ![][d=2]
- ![][\langle&space;k\rangle^3] nodes at distance ![][d=3]
- ...
- ![][\langle&space;k\rangle^d] nodes at distance ![][d]


num of nodes up to distance ![][d]

![eq.3.15][N(d)\approx1+\langle&space;k\rangle+\langle&space;k\rangle^2+\cdots+\langle&space;k\rangle^d=\frac{\langle&space;k\rangle^{d+1}-1}{\langle&space;k\rangle-1}]

max distance ![][d_{max}] or the network's diameter

![eq.3.16][N(d_{max})\approx&space;N]

assuming the ![][\langle&space;k\rangle\gg1], 

![eq.3.17][\langle&space;k\rangle^{d_{max}}\approx&space;N]

&there4; the diamter of network follows

![eq.3.18][d_{max}\approx\frac{\ln{N}}{\ln{k}}]









## 03.16 Advanced Topic 3.E Fully Connected Regime

![][(1-p)^{N_G}\approx(1-p)^N] in the ![][N_G\simeq&space;N]

the num of isolated nodes is 

![eq.3.40][I_N=N(1-p)^N=N\Big(1-\frac{N\cdot&space;p}{N}\Big)^N\approx&space;Ne^{-Np}]

for large ![][n],   
![][(1-\frac{x}{n})^n\approx&space;e^{-x}]

only one node is disconnected

![][I_N=1], eq.3.40, ![][Ne^{-Np}=1]

![eq.3.41][p=\frac{\ln{N}}{N}]

leads to eq.3.14 ![eq.3.14][\langle&space;k\rangle=\ln{N}]




##

<!-- link -->
###

[1960RényiA_ErdősP]: http://www.leonidzhukov.net/hse/2016/networks/papers/erdos-1959-11.pdf "Erdős, P. and Rényi, A., 1960. On the evolution of random graphs. Publ. Math. Inst. Hung. Acad. Sci, 5(1), pp.17-60."


<!-- figure -->
###

[fig_03_03]: http://networksciencebook.com/images/ch-03/figure-3-3.jpg "Fig.3.3 Random Networks are Truly Random"
[fig_03_04]: http://networksciencebook.com/images/ch-03/figure-3-4.jpg "Fig.3.4 Binomial vs. Poisson Degree Distribution"
[fig_03_05]: http://networksciencebook.com/images/ch-03/figure-3-5.jpg "Fig.3.5 Degree Distribution is Independent of the Network Size"
[fig_03_06]: http://networksciencebook.com/images/ch-03/figure-3-6.jpg "Fig.3.6 Degree Distribution of Real Networks "
[fig_03_07]: http://networksciencebook.com/images/ch-03/figure-3-7.jpg "Fig.3.7 Evolution of a Random Network"
[fig_03_08]: http://networksciencebook.com/images/ch-03/figure-3-8.jpg "Fig.3.8 Evolution of a Random Graph "
[fig_03_09]: http://networksciencebook.com/images/ch-03/figure-3-9.jpg "Fig.3.9 Most Real Networks are Supercritical"
[fig_03_10]: http://networksciencebook.com/images/ch-03/figure-3-10.jpg "Fig.3.10 Six Deegree of Separation"


<!-- video -->
###
[video_03_02]: http://networksciencebook.com/images/ch-03/video-3-2.m4v "Video.3.2 Evolution of a Random Network"


<!-- eq -->
###

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
[\binom{\frac{N(N-1)}{2}}{L}]: https://latex.codecogs.com/gif.latex?\binom{\frac{N(N-1)}{2}}{L} "eq.3.0"
[p_L=\binom{\frac{N(N-1)}{2}}{L}p^L(1-p)^{\frac{N(N-1)}{2}-L}]: https://latex.codecogs.com/gif.latex?p_L=\binom{\frac{N(N-1)}{2}}{L}p^L(1-p)^{\frac{N(N-1)}{2}-L} "eq.3.1"
[\langle&space;L\rangle=\sum_{L=0}^{\frac{N(N-1)}{2}}LP_L=p\frac{N(N-1)}{2}]: https://latex.codecogs.com/gif.latex?\langle&space;L\rangle=\sum_{L=0}^{\frac{N(N-1)}{2}}LP_L=p\frac{N(N-1)}{2} "eq.3.2"
[L_{max}=\frac{N(N-1)}{2}]: https://latex.codecogs.com/gif.latex?L_{max}=\frac{N(N-1)}{2}
[\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1)]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=\frac{2\langle&space;L\rangle}{N}=p(N-1) "eq.3.3"
[\langle&space;k\rangle=0]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=0
[\langle&space;k\rangle=N-1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=N-1


[p=\frac{1}{6}]: https://latex.codecogs.com/gif.latex?p=\frac{1}{6}
[N=12]: https://latex.codecogs.com/gif.latex?N=12
[L=10,&space;18,&space;8]: https://latex.codecogs.com/gif.latex?L=10,&space;18,&space;8
[p=.03]: https://latex.codecogs.com/gif.latex?p=.03
[N=100]: https://latex.codecogs.com/gif.latex?N=100
[p_x=\binom{N}{x}p^x(1-p)^{N-x}]: https://latex.codecogs.com/gif.latex?p_x=\binom{N}{x}p^x(1-p)^{N-x}
[\langle&space;x\rangle=\sum_{x=0}^Nxp_x=Np]: https://latex.codecogs.com/gif.latex?\langle&space;x\rangle=\sum_{x=0}^Nxp_x=Np "eq.3.4"
[\langle&space;x^2\rangle=\sum_{x=0}^Nx^2p_x=p(1-p)N+p^2&space;N^2]: https://latex.codecogs.com/gif.latex?\langle&space;x^2\rangle=\sum_{x=0}^Nx^2p_x=p(1-p)N+p^2&space;N^2 "eq.3.5"
[\sigma_x=\big(\langle&space;x^2\rangle-\langle&space;x\rangle^2\big)^{\frac{1}{2}}=\Big(p(1-p)N\Big)^{\frac{1}{2}}]: https://latex.codecogs.com/gif.latex?\sigma_x=\big(\langle&space;x^2\rangle-\langle&space;x\rangle^2\big)^{\frac{1}{2}}=\Big(p(1-p)N\Big)^{\frac{1}{2}} "eq.3.6"
[p_k]: https://latex.codecogs.com/gif.latex?p_k
[k]: https://latex.codecogs.com/gif.latex?k
[\binom{N-1}{k}p_k(1-p)^{N-1-k}]: https://latex.codecogs.com/gif.latex?\binom{N-1}{k}p_k(1-p)^{N-1-k}
[e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle}{k!}]: https://latex.codecogs.com/gif.latex?e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle}{k!}
[\langle&space;k\rangle=p(N-1)]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=p(N-1)
[\langle&space;k\rangle]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle
[\sigma_k]: https://latex.codecogs.com/gif.latex?\sigma_k
[p(1-p)(N-1)]: https://latex.codecogs.com/gif.latex?p(1-p)(N-1)
[\langle&space;k\rangle^{\frac{1}{2}}]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle^{\frac{1}{2}}

[i]: https://latex.codecogs.com/gif.latex?i
[p^k]: https://latex.codecogs.com/gif.latex?p^k
[N-1-k]: https://latex.codecogs.com/gif.latex?N-1-k
[(1-p)^{N-1-k}]: https://latex.codecogs.com/gif.latex?(1-p)^{N-1-k}
[\binom{N-1}{k}]: https://latex.codecogs.com/gif.latex?\binom{N-1}{k}
[p_k=\binom{N-1}{k}p^k(1-p)^{N-1-k}]: https://latex.codecogs.com/gif.latex?p_k=\binom{N-1}{k}p^k(1-p)^{N-1-k} "eq.3.7"
[\langle&space;k^2\rangle]: https://latex.codecogs.com/gif.latex?\langle&space;k^2\rangle
<!-- #Poisson-Distribution -->
[\langle&space;k\rangle\ll&space;N]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle\ll&space;N
[p_k=e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle^k}{k!}]: https://latex.codecogs.com/gif.latex?p_k=e^{-\langle&space;k\rangle}\frac{\langle&space;k\rangle^k}{k!} "eq.3.8"

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


<!-- 03.06 -->
[N_G]: https://latex.codecogs.com/gif.latex?N_G "N_G"
[p=0]: https://latex.codecogs.com/gif.latex?p=0 "p=0"
[\langle&space;k\rangle=0]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=0 "\langle&space;k\rangle=0"
[N_G=1]: https://latex.codecogs.com/gif.latex?N_G=1 "N_G=1"
[\frac{N_G}{N}\rightarrow0]: https://latex.codecogs.com/gif.latex?\frac{N_G}{N}\rightarrow0 "\frac{N_G}{N}\rightarrow0"
[p=1]: https://latex.codecogs.com/gif.latex?p=1 "p=1"
[\langle&space;k\rangle=N-1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=N-1 "\langle&space;k\rangle=N-1"
[N_G=N]: https://latex.codecogs.com/gif.latex?N_G=N "N_G=N"
[\frac{N_G}{N}=1]: https://latex.codecogs.com/gif.latex?\frac{N_G}{N}=1 "\frac{N_G}{N}=1"


[\langle&space;k\rangle=1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=1 "eq.3.10"
[0]: https://latex.codecogs.com/gif.latex?0
[N-1]: https://latex.codecogs.com/gif.latex?N-1

[p_c=\frac{1}{N-1}\approx\frac{1}{N}]: https://latex.codecogs.com/gif.latex?p_c=\frac{1}{N-1}\approx\frac{1}{N} "eq.3.11"

[0<\langle&space;k\rangle<1]: https://latex.codecogs.com/gif.latex?0<\langle&space;k\rangle<1 "0<\langle&space;k\rangle<1"
[p<\frac{1}{N}]: https://latex.codecogs.com/gif.latex?p<\frac{1}{N} "p<\frac{1}{N}"
[\langle&space;k\rangle<1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle<1 "\langle&space;k\rangle<1"
[N_G\sim\ln{N}]: https://latex.codecogs.com/gif.latex?N_G\sim\ln{N} "N_G\sim\ln{N}"
[\frac{N_G}{N}\simeq\frac{\ln{N}}{N}\rightarrow0]: https://latex.codecogs.com/gif.latex?\frac{N_G}{N}\simeq\frac{\ln{N}}{N}\rightarrow0 "\frac{N_G}{N}\simeq\frac{\ln{N}}{N}\rightarrow0"
[N\rightarrow\infty]: https://latex.codecogs.com/gif.latex?N\rightarrow\infty "N\rightarrow\infty"
[\langle&space;k\rangle=1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=1 "\langle&space;k\rangle=1"
[p=\frac{1}{N}]: https://latex.codecogs.com/gif.latex?p=\frac{1}{N}
[N_G\sim&space;N^{\frac{2}{3}}]: https://latex.codecogs.com/gif.latex?N_G\sim&space;N^{\frac{2}{3}} "N_G\sim&space;N^{\frac{2}{3}}"
[\frac{N_G}{N}\sim&space;N^{-\frac{1}{3}}]: https://latex.codecogs.com/gif.latex?\frac{N_G}{N}\sim&space;N^{-\frac{1}{3}} "\frac{N_G}{N}\sim&space;N^{-\frac{1}{3}}"
[N\rightarrow\infty]: https://latex.codecogs.com/gif.latex?N\rightarrow\infty "N\rightarrow\infty"
[N=7\times10^9]: https://latex.codecogs.com/gif.latex?N=7\times10^9 "N=7\times10^9"
[N_G\simeq\ln{N}=\ln{(7\times10^9)}\simeq22.7]: https://latex.codecogs.com/gif.latex?N_G\simeq\ln{N}=\ln{(7\times10^9)}\simeq22.7 "N_G\simeq\ln{N}=\ln{(7\times10^9)}\simeq22.7"
[N_G\sim&space;N^{\frac{2}{3}}=(7\times10^9)^{\frac{2}{3}}\simeq3\times10^6]: https://latex.codecogs.com/gif.latex?N_G\sim&space;N^{\frac{2}{3}}=(7\times10^9)^{\frac{2}{3}}\simeq3\times10^6 "N_G\sim&space;N^{\frac{2}{3}}=(7\times10^9)^{\frac{2}{3}}\simeq3\times10^6"
[\langle&space;k\rangle>1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle>1 "\langle&space;k\rangle>1"
[p>\frac{1}{N}]: https://latex.codecogs.com/gif.latex?p>\frac{1}{N} "p>\frac{1}{N}"
[\frac{N_G}{N}\sim\langle&space;k\rangle-1]: https://latex.codecogs.com/gif.latex?\frac{N_G}{N}\sim\langle&space;k\rangle-1 "eq.3.12"
[N_G\sim(p-p_c)N]: https://latex.codecogs.com/gif.latex?N_G\sim(p-p_c)N "eq.3.13"
[p_c]: https://latex.codecogs.com/gif.latex?p_c "p_c"
[\langle&space;k\rangle>\ln{N}]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle>\ln{N} "\langle&space;k\rangle>\ln{N}"
[p>\frac{\ln{N}}{N}]: https://latex.codecogs.com/gif.latex?p>\frac{\ln{N}}{N} "p>\frac{\ln{N}}{N}"
[N_G\simeq&space;N]: https://latex.codecogs.com/gif.latex?N_G\simeq&space;N "N_G\simeq&space;N"
[\langle&space;k\rangle=\ln{N}]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle=\ln{N} "eq.3.14"
[\frac{\ln{N}}{N}\rightarrow0]: https://latex.codecogs.com/gif.latex?\frac{\ln{N}}{N}\rightarrow0 "\frac{\ln{N}}{N}\rightarrow0"

<!-- Box 3-5 Network Evolution in Graph Theory -->
[p(N)]: https://latex.codecogs.com/gif.latex?p(N) "p(N)"
[N^z]: https://latex.codecogs.com/gif.latex?N^z "N^z"
[z]: https://latex.codecogs.com/gif.latex?z "z"
[-\infty,0]: https://latex.codecogs.com/gif.latex?[-\infty,0] "[-\infty,0]"


<!-- 03.07 -->
[\ln{N}]: https://latex.codecogs.com/gif.latex?\ln{N} "\ln{N}"


<!-- 03.08 -->
[d=1]: https://latex.codecogs.com/gif.latex?d=1 "d=1"
[\langle&space;k\rangle^2]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle^2 "\langle&space;k\rangle^2"
[d=2]: https://latex.codecogs.com/gif.latex?d=2 "d=2"
[\langle&space;k\rangle^3]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle^3 "\langle&space;k\rangle^3"
[d=3]: https://latex.codecogs.com/gif.latex?d=3 "d=3"
[\langle&space;k\rangle^d]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle^d "\langle&space;k\rangle^d"
[d]: https://latex.codecogs.com/gif.latex?d "d"
[N(d)\approx1+\langle&space;k\rangle+\langle&space;k\rangle^2+\cdots+\langle&space;k\rangle^d=\frac{\langle&space;k\rangle^{d+1}-1}{\langle&space;k\rangle-1}]: https://latex.codecogs.com/gif.latex?N(d)\approx1+\langle&space;k\rangle+\langle&space;k\rangle^2+\cdots+\langle&space;k\rangle^d=\frac{\langle&space;k\rangle^{d+1}-1}{\langle&space;k\rangle-1} "eq.3.15"
[d_{max}]: https://latex.codecogs.com/gif.latex?d_{max} "d_{max}"
[N(d_{max})\approx&space;N]: https://latex.codecogs.com/gif.latex?N(d_{max})\approx&space;N "eq.3.16"
[\langle&space;k\rangle\gg1]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle\gg1 "\langle&space;k\rangle\gg1"
[\langle&space;k\rangle^{d_{max}}\approx&space;N]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle^{d_{max}}\approx&space;N "eq.3.17"
[d_{max}\approx\frac{\ln{N}}{\ln{k}}]: https://latex.codecogs.com/gif.latex?d_{max}\approx\frac{\ln{N}}{\ln{k}} "eq.3.18"






<!-- 03.16 -->
[(1-p)^{N_G}\approx(1-p)^N]: https://latex.codecogs.com/gif.latex?(1-p)^{N_G}\approx(1-p)^N "(1-p)^{N_G}\approx(1-p)^N"
[N_G\simeq&space;N]: https://latex.codecogs.com/gif.latex?N_G\simeq&space;N "N_G\simeq&space;N"
[I_N=N(1-p)^N=N\Big(1-\frac{N\cdot&space;p}{N}\Big)^N\approx&space;Ne^{-Np}]: https://latex.codecogs.com/gif.latex?I_N=N(1-p)^N=N\Big(1-\frac{N\cdot&space;p}{N}\Big)^N\approx&space;Ne^{-Np} "eq.3.40"
[(1-\frac{x}{n})^n\approx&space;e^{-x}]: https://latex.codecogs.com/gif.latex?(1-\frac{x}{n})^n\approx&space;e^{-x} "(1-\frac{x}{n})^n\approx&space;e^{-x}"
[I_N=1]: https://latex.codecogs.com/gif.latex?I_N=1 "I_N=1"
[Ne^{-Np}=1]: https://latex.codecogs.com/gif.latex?Ne^{-Np}=1 "Ne^{-Np}=1"
[p=\frac{\ln{N}}{N}]: https://latex.codecogs.com/gif.latex?p=\frac{\ln{N}}{N} "p=\frac{\ln{N}}{N}"





<!-- 
https://latex.codecogs.com/gif.latex?\inline&space;
https://latex.codecogs.com/gif.latex?
-->

<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->