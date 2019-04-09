<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c03
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-06 20:27:3
Modified: 	2019-04-09 11:13:1
-----
Copyright (c) 2019 shumez
-->

# 03 Random Networks

## Contents

01. [Introduction](#0301_introduction)
02. [The Random Network Model](#0302_the_random_network_model)
    * [Box 3-1 Defining Random Networks](#box_3-1_defining_random_networks)
    * [Box 3-2 Random Networks: a Brief History](#box_3-2_random_networks_a_brief_history)
03. [Number of Links](#0303_number_of_links)
    * [Box 3-3 Binomial Distribution: Mean and Variance](#box_3-3_binomial_distribution_mean_and_variance)
04. [Degree Distribution](#0304_degree_distribution)
    * [Binomial Distribution](#binomial_distribution)
    * [Poisson Distribution](#poisson_distribution)
05. [Real Networks are Not Poisson](#0305_real_networks_are_not_poisson)
    * [Box 3-4 Why are Hubs Missing?](#box_3-4_why_are_hubs_missing)
06. [The Evolution of a Random Network](#0306_the_evolution_of_a_random_network)
    * [Box 3-5 Network Evolution in Graph Theory](#box_3-5_network_evolution_in_graph_theory)
07. [Real Networks are Supercritical](#0307_real_networks_are_supercritical)
08. [Small Worlds](#0308_small_worlds)
    * [Box 3-6 19 Degrees of Separation](#box_3-6_19_degrees_of_separation)
    * [Box 3-7 Six Degrees: Experimental Confirmation](#box_3-7_six_degrees_experimental_confirmation)
    * [Box 3-8 19 Degrees of the WWW](#box_3-8_19_degrees_of_the_www)
09. [Clustering Coefficient](#0309_clustering_coefficient)
    * [Box 3-9 Watts-Strogatz Model](#box_3-9_watts-strogatz_model)
10. [Summary: Real Networks are Not Random](#0310_summary_real_networks_are_not_random)


* 16 [Advanced Topic 3.E Fully Connected Regime](#0316_Advanced_Topic_3E_Fully_Connected_Regime)


## 03.01 Introduction


## 03.02 The Random Network Model

\(N\) nodes, connected w/ probability \(p\) 

### Box 3-1 Defining Random Networks

- \(G(N,L)\) model :
    - \(N\) labeled node are connedted with \(L\) randomly placed links
    - fixes the total num of links \(L\)
    - average degree of node \(\langle k \rangle = \frac{2L}{N}\)
- \(G(N,p)\) model :
    - \(N\) labeled nodes is connected with probability \(p\)
    - fixes prob \(p\)


### 

**random graph** (**random network**, **Erdős-Rényi network**)


### Box 3-2 Random Networks: a Brief History

- Anatol Rapoport
- *Random graph theory* Pál Erdős and Alfréd Rényi
- Edgar Nelson Gilbert 


## 03.03 Number of Links

- prob that \(L\) of attempts to connect \(\frac{N(N-1)}{2}\) pairs of nodes have result in link, is \(p^L\)
- prob that the remaining \(\frac{N(N-1)}{2}\) pairs of nodes have  not resulted in a link is
    \((1-p)^{\frac{N(N-1)}{2}-L}\)
- conmbinational factor
    <!-- \[ \binom{\frac{N(N-1)}{2}}{L} \tag{3.0} \] -->
    \[\binom{\frac{N(N-1)}{2}}{L} \tag{3.0}\]

\[ p_L = \binom{\frac{N(N-1)}{2}}{L} p^L (1 - p)^{\frac{N (N - 1)}{2} - L} \tag{3.1} \]



expected num of links

\[ \langle L \rangle = \sum_{L=0}^{\frac{N(N-1)}{2}} LP_L = p \frac{N(N-1)}{2} \tag{3.2} \]


\( L_{max} = \frac{N(N-1)}{2} \)



\[ \langle k \rangle = \frac{2 \langle L \rangle}{N} = p (N - 1) \tag{3.3} \]


from \(\langle k \rangle = 0\) to \(\langle k\rangle = N-1\)

[![fig.3.3][fig_03_03]][fig_03_03]

\(p = \frac{1}{6}\), \(N=12\), \(L = 10, 18, 8\)

\(p = .03\), \(N = 100\)


### Box 3-3 Binomial Distribution: Mean and Variance

\[ p_x = \binom{N}{x} p^x (1-p)^{N-x} \]

\[ \langle x \rangle = \sum_{x=0}^N xp_x = Np \tag{3.4} \]

\[ \langle x^2 \rangle = \sum_{x=0}^N x^2 p_x = p(1-p)N + p^2 N^2 \tag{3.5} \]


standard deviation

\[ 
    \begin{align*}
        \sigma_x 
        &= \big( \langle x^2 \rangle - \langle x \rangle^2 \big)^{\frac{1}{2}} \\
        &= [ p(1 - p) N ]^{\frac{1}{2}} 
    \end{align*}
    \tag{3.6} 
\]



## 03.04 Degree Distribution

degree dist \(p_k\), degree \(k\)


|               |               | Binominal                                                 | Poisson |
|--------------:|:-------------:|:---------------------------------------------------------:|:------------------------------------------:|
| degree dist   | \(p_k\)      | \(\binom{N-1}{k}p_k(1-p)^{N-1-k}\)   | \(e^{-\langle k \rangle} \frac{\langle k \rangle}{k!}\) |
| peak at       | \(k\)        | \(\langle k \rangle = p(N-1)\)                        | \(\langle k \rangle\)               |
| width         | \(\sigma_k\) | \(p(1-p)(N-1)\)                                          | \(\langle k \rangle^{\frac{1}{2}}\) |



[![fig.3.4][fig_03_04]][fig_03_04]


### Binomial Distribution

prob that node \(i\) has \(k\) links is product of 3 terms:

1. prob that \(k\) of its links are present / \(p^k\)
2. prob that remaining (\(N-1-k\)) links are missing / \((1-p)^{N-1-k}\)
3. 
    \[ \binom{N-1}{k} \]

\[ p_k = \binom{N-1}{k} p^k (1-p)^{N-1-k} \tag{3.7} \]

average degree \(\langle k \rangle\)
second moment \(\langle k^2 \rangle\) & variance \(\sigma_k\)


### Poisson Distribution

sparse networks: \(\langle k \rangle \ll N\)

eq.3.7 is approx'd by Poisson dist

\[ p_k = e^{- \langle k \rangle } \frac{\langle k \rangle^k}{k!} \tag{3.8} \]


**degree distributioin of a random network**

[![fig.3.5][fig_03_05]][fig_03_05]
> The degree distribution of a random network with ‹k› = 50 and N = 102, 103, 104.
> Small Networks: Binomial
> For a small network (N = 102) the degree distribution deviates significantly from the Poisson form (3.8), as the condition for the Poisson approximation, N»‹k›, is not satisfied. Hence for small networks one needs to use the exact binomial form (3.7) (green line).

> Large Networks: Poisson
> For larger networks (N = 103, 104) the degree distribution becomes indistinguishable from the Poisson prediction (3.8), shown as a continuous grey line. Therefore for large N the degree distribution is independent of the network size. In the figure we averaged over 1,000 independently generated random networks to decrease the noise.


## 03.05 Real Networks are Not Poisson

social network
\(\langle k \rangle \approx 1000\), \(N \approx 7 \times10^9\) of individuals

\(k_{\text{max}} = 1185\) accuaitances

\(k_{\text{min}} = 816\)

despersion of random network is \(\sigma_k = \langle k \rangle^{\frac{1}{2}}\), 
for \(\langle k \rangle = 1000\) \(\sigma_k = 31.62\)
\(\langle k \rangle \pm \sigma_k\) range 

*in a large random network the degree of most nodes is in the narrow vicinity of* \(\langle k \rangle\)


### Box 3-4 Why are Hubs Missing?

\(\frac{1}{k!}\)

the Stirling approx

\(k! \sim \sqrt{2\pi k} \bigg(\frac{k}{e}\bigg)^k\)

rewrite eq.3.8  as:

\[p_k = \frac{e^{- \langle k \rangle}}{\sqrt{2\pi k}}\bigg(\frac{e\langle k \rangle}{k}\bigg)^k \tag{3.9} \]

\[ k > e \langle k \rangle \]


### 

[![figure.3.6][fig_03_06]][fig_03_06]


## 03.06 The Evolution of a Random Network

the size of the largest conneted cluster w/i the network, \(N_G\) varies w/ \(\langle k \rangle\)

- for \(p=0\) we have \(\langle k \rangle = 0\), &there4; \(N_G = 1\) and \(\frac{N_G}{N} \rightarrow 0 \) for large \(N\)
- for \(p = 1\) we have \(\langle k \rangle = N-1\), complete graph, &there4; \(N_G = N\) and \(\frac{N_G}{N} = 1\)

<!-- ![video.3.2][video_03_02] -->

<iframe width="560" height="315" src="http://networksciencebook.com/images/ch-03/video-3-2.m4v" id="video_03_02" allowfullscreen></iframe>

grow from \(N_G = 1\) to \(N_G = N\) if \(\langle k \rangle\) increase from \(0\) to \(N-1\)


[Erdős P., Rényi A., 1960][1960RényiA_ErdősP] condition for teh emergence of the giant component is ([Erdős P., Rényi A., 1960][1960RényiA_ErdősP]):

\[\langle k \rangle = 1 \tag{3.10}\]

express eq.3.10 in terms of \(p\) using eq.3.3 \(\langle k \rangle = \frac{2 \langle L \rangle}{N} = p(N-1) \)


\[ p_c=\frac{1}{N-1}\approx\frac{1}{N} \tag{3.11}\]

the larger network, the smaller \(p\) is sufficient for the giant component

4 regimes: 

**Subcritical regime**: \(0 < \langle k \rangle < 1\) (\(p < \frac{1}{N}\))

for \(\langle k \rangle < 1\), 
\(N_G \sim \ln{N}\)

&there4; \(\frac{N_G}{N} \simeq \frac{\ln{N}}{N} \rightarrow 0\), \([N \rightarrow \infty\)


**Critical point**: \(\langle k \rangle = 1\) (\(p = \frac{1}{N}\))

size of the largest component is
\(N_G \sim N^{\frac{2}{3}}\)

\(\frac{N_G}{N} \sim N^{-\frac{1}{3}}\) in the \(N \rightarrow \infty\) limit

e.g., \(N = 7 \times 10^9\) nodes

for \(\langle k \rangle < 1\), 
\(N_G \simeq \ln{N} = \ln{(7\times10^9)} \simeq 22.7\)

for \(\langle k \rangle = 1\), 
\(N_G \sim N^{\frac{2}{3}} = (7 \times 10^9)^{\frac{2}{3}} \simeq 3\times10^6\)


![fig.3.7][fig_03_07]


**Supercritical Regime**: \(\langle k \rangle > 1\) (\(p > \frac{1}{N}\))


\[\frac{N_G}{N} \sim \langle k \rangle-1 \tag{3.12}\]

or


\[N_G \sim (p-p_c)N \tag{3.13}\]

where \(p_c\) is given by eq.3.11 (\(p_c = \frac{1}{N-1} \approx \frac{1}{N}\))


**Connected Regime**: \(\langle k \rangle > \ln{N}\) (\(p > \frac{\ln{N}}{N}\))

\[N_G \simeq N\]

\[\langle k \rangle = \ln{N} \tag{3.14}\]

\(\frac{\ln{N}}{N} \rightarrow 0\) for large \(N\)


### Box 3-5 Network Evolution in Graph Theory

\(p(N)\) scales as \(N^z\) where \(z\) is tunable param \([-\infty, 0]\)

![fig.3.8][fig_03_08]


## 03.07 Real Networks are Supercritical


- \(\langle k \rangle = 1\) 
- \(\langle k \rangle > \ln{N}\)

Network	                | \(N\)	| \(L\)	    | \(\langle K \rangle\)| \(\ln{N}\)   |
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


- \(\langle k \rangle\) nodes at distance \(d = 1\)
- \(\langle k \rangle^2\) nodes at distance \(d = 2\)
- \(\langle k \rangle^3\) nodes at distance \(d = 3\)
- ...
- \(\langle k \rangle^d\) nodes at distance \(d\)


num of nodes up to distance \(d\)


\[ 
    \begin{align*}
        N(d) 
        &\approx 1 + \langle k \rangle + \langle k \rangle^2 + \cdots + \langle k \rangle^d \\
        &= \frac{\langle k \rangle^{d+1} - 1}{\langle k \rangle - 1}
    \end{align*}
    \tag{3.15}
\]

max distance \(d_{max}\) or the network's diameter

\[N(d_{max}) \approx N \tag{3.16}\]

assuming the \(\langle k \rangle \gg 1\), 

\[\langle k \rangle^{d_{max}} \approx N \tag{3.17}\]

&there4; the diamter of network follows


\[d_{max} \approx \frac{\ln{N}}{\ln{k}} \tag{3.18}\]

- average distance between 2 randomly chosen nodes \(\langle d \rangle\)

    the small world property is defined by
    
    \[\langle d \rangle \approx \frac{\ln{N}}{\ln{\langle k \rangle}} \tag{3.19}\]

- \(\ln{N} \ll N\), 
    *average path length or the diameter depends logarithmically on the system size*

- \(\frac{1}{\ln{\langle k \rangle}}\) imply the denser the network, the smaller the distance

- in real networks, systematic corrections to eq.3.19


[![fig.3.11][fig_03_11]][fig_03_11]

- 1D: \(d_{max} \sim \langle d \rangle \sim N\)
- 2D: \(d_{max} \sim \langle d \rangle \sim N^{\frac{1}{2}}\)
- 3D: \(d_{max} \sim \langle d \rangle \sim N^{\frac{1}{3}}\)
- 4D: \(d_{max} \sim \langle d \rangle \sim N^{\frac{1}{d}}\)

\(N \approx 7 \times 10^9\), \(\langle k \rangle \approx 10^3\)

\(\langle d \rangle \approx \frac{\ln{7\times10^9}}{\ln{10^3}} = 3.28\)

([de Sola Pool, I., Kochen, M., 1978][1978KochenM_deSolaPoolI] [20])


### Box 3-6 19 Degrees of Separation

**finite size scaling** ([Albert, R., 1999][1999BarabásiAL_JeongH_AlbertR])

\(\langle d \rangle \approx 0.35 + 0.89 \ln{N}\)

\(\langle d \rangle \approx 18.69\) ([Lawrence, S., Giles, C.L., 1999][1999GilesCL_LawreneceS])

*19 degrees of separation*


### 

Network	| \(N\)| \(L\)| \(\langle k \rangle\)| \(\langle d \rangle\)| \(d_{max}\)| \(\frac{\ln{N}}{\ln{\langle k \rangle}}\)
--------|--:|--:|------:|------:|------:|----------:
Internet	            | 192,244	| 609,066	    | 6.34	| 6.98	| 26	| 6.58
WWW	                    | 325,729	| 1,497,134	    | 4.60	| 11.27	| 93	| 8.31
Power Grid	            | 4,941	    | 6,594	        | 2.67	| 18.99	| 46	| 8.66
Mobile-Phone Calls	    | 36,595	| 91,826	    | 2.51	| 11.72	| 39	| 11.42
Email	                | 57,194	| 103,731	    | 1.81	| 5.88	| 18	| 18.4
Science Collaboration	| 23,133	| 93,437	    | 8.08	| 5.35	| 15	| 4.81
Actor Network	        | 702,388	| 29,397,908	| 83.71	| 3.91	| 14	| 3.04
Citation Network	    | 449,673	| 4,707,958	    | 10.43	| 11.21	| 42	| 5.55
E. Coli Metabolism	    | 1,039	    | 5,802	        | 5.58	| 2.98	| 8	    | 4.04
Protein Interactions	| 2,018	    | 2,930	        | 2.90	| 5.61	| 14	| 7.14


### Box 3-7 Six Degrees: Experimental Confirmation

[![fig.3.12][fig_03_12]][fig_03_12]


### Box 3-8 19 Degrees of the WWW
[![fig.box.3.8][fig_box_3_8]][fig_box_3_8]


## 03.09 Clustering Coefficient

clustering coefficient \(C_i\), the density of the links in node \(i\)'s immediate neighborhood

expected number of links \(L_i\) 

\[\langle\ L_i \rangle = p \frac{k_i(k_i-1)}{2} \tag{3.20}\]

local clustering coefficient:

\[
    \begin{align*}
        C_i 
        &= \frac{2\langle L_i \rangle}{k_i(k_i - 1)} \\
        &= p \\
        &= \frac{\langle k \rangle}{N}
    \end{align*} 
    \tag{3.21}
\]


plot \(\frac{\langle C \rangle}{\langle k \rangle}\) in fn of \(N\) 

\(\frac{\langle C \rangle}{\langle k \rangle}\) NOT decrease as \(N^{-1}\)


[![fig.3.13][fig_03_13]][fig_03_13]


### Box 3-9 Watts-Strogatz Model

[![fig.3.14][fig_03_14]][fig_03_14]

- Small World Property
    average distance depends logarithmically on \(N\)
- High Clustering
    average clustering coef of real netw is higher than expected for a rand netw of similar \(N\) and \(L\)

**Watts-Strogatz model** (small-world model) 
interpolate 

- Regular lattice: 
    - High clustering
    - Small-world property(-)
- Random netw: 
    - Low clustering
    - Small-world property(+)


## 03.10 Summary: Real Networks are Not Random







## 03.16 Advanced Topic 3.E Fully Connected Regime

\((1-p)^{N_G} \approx (1-p)^N\) in the \(N_G \simeq N\)

the num of isolated nodes is 

\[
    \begin{align*}
        I_N 
        &= N (1-p)^N \\
        &= N \Big(1 - \frac{N \cdot p}{N} \Big)^N \\&
        \approx Ne^{-Np}
    \end{align*} 
    \tag{3.40}
\]

for large \(n\),   
\((1 - \frac{x}{n})^n \approx e^{-x}\)

only one node is disconnected

\(I_N = 1\), eq.3.40, \(Ne^{-Np} = 1\)

\[p = \frac{\ln{N}}{N} \tag{3.41}\]

leads to eq.3.14 \(\langle k \rangle = \ln{N}\)




##

<!-- link -->
###

[1960RényiA_ErdősP]: http://www.leonidzhukov.net/hse/2016/networks/papers/erdos-1959-11.pdf "Erdős, P. and Rényi, A., 1960. On the evolution of random graphs. Publ. Math. Inst. Hung. Acad. Sci, 5(1), pp.17-60."
[1978KochenM_deSolaPoolI]: https://www.sfu.ca/cmns/courses/marontate/2009/801/ClassFolders/jmckinnon/(0)%20Contacts%20and%20influence.pdf "de Sola Pool, I. and Kochen, M., 1978. Contacts and influence. Social networks, 1(1), pp.5-51."
[1999BarabásiAL_JeongH_AlbertR]: http://barabasi.com/f/65.pdf "21"
[1999GilesCL_LawreneceS]: https://homepage.univie.ac.at/juan.gorraiz/Vortrag/21987.pdf "Lawrence, S. and Giles, C.L., 1999. Accessibility of information on the web. Nature, 400(6740), p.107."


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
[fig_03_11]: http://networksciencebook.com/images/ch-03/figure-3-11.jpg "Fig.3.11 Why are Small Worlds Surprising?"
[fig_03_12]: http://networksciencebook.com/images/ch-03/figure-3-12.jpg "Fig.3.12 Six Degrees? From Milgram to Facebook"
[fig_box_3_8]: http://networksciencebook.com/images/ch-03/figure-box-3-8.jpg "19 Degrees of the WWW"
[fig_03_13]: http://networksciencebook.com/images/ch-03/figure-3-13.jpg "Fig.3.13 Clustering in Real Networks"
[fig_03_14]: http://networksciencebook.com/images/ch-03/figure-3-14.jpg "Fig.3.14 The Watts-Strogatz Model"


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
[\langle&space;d\rangle]: https://latex.codecogs.com/gif.latex?\langle&space;d\rangle "\langle&space;d\rangle"
[\langle&space;d\rangle\approx\frac{\ln{N}}{\ln{\langle&space;k\rangle}}]: https://latex.codecogs.com/gif.latex?\langle&space;d\rangle\approx\frac{\ln{N}}{\ln{\langle&space;k\rangle}} "eq.3.19"
[\ln{N}\ll&space;N]: https://latex.codecogs.com/gif.latex?\ln{N}\ll&space;N "\ln{N}\ll&space;N"
[\frac{1}{\ln{\langle&space;k\rangle}}]: https://latex.codecogs.com/gif.latex?\frac{1}{\ln{\langle&space;k\rangle}} "\frac{1}{\ln{\langle&space;k\rangle}}"
[d_{max}\sim\langle&space;d\rangle\sim&space;N]: https://latex.codecogs.com/gif.latex?d_{max}\sim\langle&space;d\rangle\sim&space;N "d_{max}\sim\langle&space;d\rangle\sim&space;N"
[d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{2}}]: https://latex.codecogs.com/gif.latex?d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{2}} "d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{2}}"
[d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{3}}]: https://latex.codecogs.com/gif.latex?d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{3}} "d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{3}}"
[d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{d}}]: https://latex.codecogs.com/gif.latex?d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{d}} "d_{max}\sim\langle&space;d\rangle\sim&space;N^{\frac{1}{d}}"
[N\approx7\times10^9]: https://latex.codecogs.com/gif.latex?N\approx7\times10^9 "N\approx7\times10^9"
[\langle&space;k\rangle\approx10^3]: https://latex.codecogs.com/gif.latex?\langle&space;k\rangle\approx10^3 "\langle&space;k\rangle\approx10^3"
[\langle&space;d\rangle\approx\frac{\ln{7\times10^9}}{\ln{10^3}}=3.28]: https://latex.codecogs.com/gif.latex?\langle&space;d\rangle\approx\frac{\ln{7\times10^9}}{\ln{10^3}}=3.28 "\langle&space;d\rangle\approx\frac{\ln{7\times10^9}}{\ln{10^3}}=3.28"

<!-- Box 3.6 -->
[\langle&space;d\rangle\approx0.35+0.89\ln{N}]: https://latex.codecogs.com/gif.latex?\langle&space;d\rangle\approx0.35+0.89\ln{N} "\langle&space;d\rangle\approx0.35+0.89\ln{N}"
[\langle&space;d\rangle\approx18.69]: https://latex.codecogs.com/gif.latex?\langle&space;d\rangle\approx18.69 "\langle&space;d\rangle\approx18.69"
[\frac{\ln{N}}{\ln{\langle&space;k\rangle}}]: https://latex.codecogs.com/gif.latex?\frac{\ln{N}}{\ln{\langle&space;k\rangle}} "\frac{\ln{N}}{\ln{\langle&space;k\rangle}}"


<!-- 03.09 -->
[C_i]: https://latex.codecogs.com/gif.latex?C_i "C_i"
[L_i]: https://latex.codecogs.com/gif.latex?L_i "L_i"
[\langle&space;L_i\rangle=p\frac{k_i(k_i-1)}{2}]: https://latex.codecogs.com/gif.latex?\langle&space;L_i\rangle=p\frac{k_i(k_i-1)}{2} "eq.3.20"
[C_i=\frac{2\langle&space;L_i\rangle}{k_i(k_i-1)}=p=\frac{\langle&space;k\rangle}{N}]: https://latex.codecogs.com/gif.latex?C_i=\frac{2\langle&space;L_i\rangle}{k_i(k_i-1)}=p=\frac{\langle&space;k\rangle}{N} "eq.3.21"
[\frac{\langle&space;C\rangle}{\langle&space;k\rangle}]: https://latex.codecogs.com/gif.latex?\frac{\langle&space;C\rangle}{\langle&space;k\rangle} "\frac{\langle&space;C\rangle}{\langle&space;k\rangle}"
[N^{-1}]: https://latex.codecogs.com/gif.latex?N^{-1} "N^{-1}"





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