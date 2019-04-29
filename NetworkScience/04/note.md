<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/NetworkScience/04
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-28 19:54:5
Modified: 	2019-04-29 16:14:4
-----
Copyright (c) 2019 shumez
-->

# [04. The Scale-Free Property][c04]

## Contents

* [04.01. Introduction](#0401_introduction)
* [04.02. Power Laws and Scale-Free Networks](#0402_power_laws_and_scale-free_networks)
    * [04.02.01. Discrete Formalism](#040201_discrete_formalism)
    * [04.02.02. Continuum Formalism](#040202_continuum_formalism)
    * [Box 4-1 The 80/20 Rule and the Top One Percent](#box_4-1_the_8020_rule_and_the_top_one_percent)
* [04.03. Hubs](#0403_hubs)
    * [04.03.01. The Largest Hub](#040301_the_largest_hub)


## 04.01. Introduction

[![fig.4.1][fig_04_01]][fig_04_01]

scale-free vs. random network

* highly connected; hubs forbidden vs. small-degree, few hubs w/ large number of links

**scale-free network**

## 04.02. Power Laws and Scale-Free Networks

[fig.4.2][fig_04_02] indicates

\[ p_k \sim k^{-\gamma} \tag{4.1} \]

eq.4.1: **power law dist** 

**degree exponent** \(\gamma\)

\[ \log{p_k} \sim - \gamma \log{k} \tag{4.2} \]

\( \log{p_k} \) depends linealy on \( \log{k} \)


[![fig.4.2][fig_04_02]][fig_04_02]

* \( γ_{in} = 2.1 \), \( γ_{out} = 2.45 \)
* \( \langle k_{in} \rangle = \langle k_{out} \rangle = 4.60 \)

out-degree \(k_{out}\), in-degree \(k_{in}\)

\[ p_{k_{in}} \sim k^{- \gamma_{in}} \tag{4.3} \]

\[ p_{k_{out}} \sim k^{- \gamma_{out}} \tag{4.4} \]

\(\gamma_{in}\) and \(\gamma_{out}\)

e.g., \(\gamma_{in} \approx 2.1\), \(\gamma_{out} \approx 2.45\)


**scale-free** ([Barabási, A.L., Albert R., 1999][1999AlbertR_BarabásiAL]) defined as:

A scale-free network is a network whose **degree distribution follows a power law**


### 04.02.01. Discrete Formalism

prob \(p_k\), \(k\) links

\[ p_k = C k^{- \gamma} \tag{4.5} \]

constant \(C\) is determined by the normalization cond

\[ \sum_{k=1}^\infty {p_k} = 1 \tag{4.6} \]

using eq.4.5, 

\[ C \sum_{k=1}^\infty {k^{- \gamma}} = 1 \]

hence

\[ C = \frac{1}{\sum_{k=1}^\infty {k^{\gamma}}} = \frac{1}{\zeta(\gamma)} \tag{4.7} \]

**[Riemann-zeta fn]** \(\zeta(\gamma) = \sum_{k=1}^\infty{\frac{1}{k^{\gamma}}}\)

for \(k>0\), the discrete power-law dist:

\[ p_k = \frac{k^{- \gamma}}{\zeta(\gamma)} \tag{4.8} \]



### 04.02.02. Continuum Formalism

\[ p(k) = C k^{- \gamma} \tag{4.9} \]

using normalization condition

\[ \int_{C_{min}}^\infty{p(k)} \mathrm{d}k = 1 \tag{4.10} \]

eq.4.9  
obtain

\[ 
    \begin{align*}
        \int_{k_{\min}}^\infty{p(k)} \mathrm{d}k &= \int_{k_{\min}}^\infty{Ck^{-\gamma}} \mathrm{d}k \\
        1 &= C \int_{k_{\min}}^\infty{k^{-\gamma}} \mathrm{d}k 
    \end{align*}
\]

\[ C = \frac{1}{\int_{k_{min}}^\infty{k^{-\gamma} \mathrm{d}k}} = (\gamma - 1) k_{min}^{\gamma - 1} \tag{4.11} \]


\[ p(k) = (\gamma - 1) k_{min}^{\gamma - 1} k^{-\gamma} \tag{4.12} \]



\[ \int_{k_1}^{k_2}{p(k)} \mathrm{d}k \tag{4.13} \]

radaomly chosen node has degree \([k_1, k_2]\)


### Box 4-1 The 80/20 Rule and the Top One Percent

<!-- [![fig.4.3][fig_04_03]][fig_04_03] -->

## 04.03. Hubs

high-\(k\) region of \(p_k\)

* for small \(k\), power law is above the Poisson fn
* for \(k\) in the vicinity of \(\langle k \rangle\), 
* for large \(k\), 

prob (node with \(k=100\))   
\(p_{100}\approx 10^{-94}\) in Poisson dist  
\(p_{100} \approx 4 \times 10^{-4}\) in power law

\[ N_{k≥100} = 10^{12} \sum_{k=100}^\infty{\frac{(4.6)^k}{k!} e^{-4.6}} \simeq 10^{-82} \tag{4.14} \]


[![fig.4.4][fig_04_04]][fig_04_04]


### 04.03.01. The Largest Hub

WWW is estimated to be \(N \approx 10^{12}\) nodes  
Earth;s population about \(N \approx 7 \times 10^9\)  
human cell \(N \approx 20000\) genes

maximum degree \(k_{max}\) **natural cutoff** of the degree dist \(p_k\)

exponential dist

\[ p(k)  = Ce^{- \lambda k} \]

minimum degree \(k_{min}\) 

\[ \int_{k_{min}}^\infty{p(k)} \mathrm{d}k = 1 \tag{4.15} \]
\[ 
    \begin{align*} 
        \int_{k_{min}}^\infty{C e^{- \lambda k}} 
        &= \Big[ - \frac{1}{\lambda} C e^{- \lambda k} \Big]_{k_{min}}^\infty \\
        &= [ - \frac{1}{\lambda} C e^{- \lambda\infty}] - [ - \frac{1}{\lambda} C e^{- \lambda k_{min}}] \\
        &= 0 + \frac{1}{\lambda} C e^{- \lambda k_{min}} &= 1 \\
        C &= \lambda e^{\lambda k_{min}}
    \end{align*} 
    \tag{4.15.1}
\]

provide \( C = \lambda e^{\lambda k_{min}} \)

\(k_{max}\) is \(\frac{1}{N}\):

\[ \int_{k_{min}}^\infty{p(k) \mathrm{d}k} = \frac{1}{N} \tag{4.16} \]

eq.4.16 yields

\[ k_{max} = k_{min} + \frac{\ln{N}}{\lambda} \tag{4.17} \]

\(\ln{N}\)


[![fig.4.5][fig_04_05]][fig_04_05]


## 

<!-- link -->
[c04]: http://networksciencebook.com/chapter/4
[1999AlbertR_BarabásiAL]: https://arxiv.org/pdf/cond-mat/9910332.pdf%3Forigin%3Dpublication_detail "Barabási, A.L. and Albert, R., 1999. Emergence of scaling in random networks. science, 286(5439), pp.509-512."

[Riemann-zeta fn]: https://en.wikipedia.org/wiki/Riemann_zeta_function

<!-- figure -->
[fig_04_01]: http://networksciencebook.com/images/ch-04/figure-4-1.jpg "Fig.4.1 The Topology of the World Wide Web"
[fig_04_02]: http://networksciencebook.com/images/ch-04/figure-4-2.jpg "Fig.4.2 The Degree Distribution of the WWW"
[fig_04_03]: http://networksciencebook.com/images/ch-04/figure-4-3.jpg "Fig.4.3 Vilfredo Federico Damaso Pareto (1848 – 1923) "
[fig_04_04]: http://networksciencebook.com/images/ch-04/figure-4-4.jpg "Fig.4.4 Poisson vs. Power-law Distributions"
[fig_04_05]: http://networksciencebook.com/images/ch-04/figure-4-5.jpg "Fig.4.5 Hubs are Large in Scale-free Networks "


<!-- eq -->

<!-- 02 -->
[p_k\sim&space;k^{-\gamma}]: https://latex.codecogs.com/gif.latex?p_k\sim&space;k^{-\gamma} "eq.4.1"
[\log{p_k}\sim-\gamma\log{k}]: https://latex.codecogs.com/gif.latex?\log{p_k}\sim-\gamma\log{k} "eq.4.2" 
[\gamma]: https://latex.codecogs.com/gif.latex?\gamma "\gamma"
[\log{p_k}]: https://latex.codecogs.com/gif.latex?\log{p_k} "\log{p_k}"
[\log{k}]: https://latex.codecogs.com/gif.latex?\log{k} "\log{k}"
[k_{out}]: https://latex.codecogs.com/gif.latex?k_{out} "k_{out}"
[k_{in}]: https://latex.codecogs.com/gif.latex?k_{in} "k_{in}"
[p_{k_{in}}\sim&space;k^{-\gamma_{in}}]: https://latex.codecogs.com/gif.latex?p_{k_{in}}\sim&space;k^{-\gamma_{in}} "eq.4.3" 
[p_{k_{out}}\sim&space;k^{-\gamma_{out}}]: https://latex.codecogs.com/gif.latex?p_{k_{out}}\sim&space;k^{-\gamma_{out}} "eq.4.4"
[\gamma_{in}]: https://latex.codecogs.com/gif.latex?\gamma_{in} "\gamma_{in}"
[\gamma_{out}]: https://latex.codecogs.com/gif.latex?\gamma_{out} "\gamma_{out}"
[\gamma_{in}\approx2.1]: https://latex.codecogs.com/gif.latex?\gamma_{in}\approx2.1 "\gamma_{in}\approx2.1"
[\gamma_{out}\approx2.45]: https://latex.codecogs.com/gif.latex?\gamma_{out}\approx2.45 "\gamma_{out}\approx2.45"

<!-- Discrete Formalism -->
[p_k]: https://latex.codecogs.com/gif.latex?p_k "p_k"
[k]: https://latex.codecogs.com/gif.latex?k "k"
[p_k=Ck^{-\gamma}]: https://latex.codecogs.com/gif.latex?p_k=Ck^{-\gamma} "eq.4.5"
[C]: https://latex.codecogs.com/gif.latex?C "C"
[\sum_{k=1}^\imfty{p_k}=1]: https://latex.codecogs.com/gif.latex?\sum_{k=1}^\imfty{p_k}=1 "eq.4.6"
[C\sum_{k=1}^\infty{k^{-\gamma}}=1]: https://latex.codecogs.com/gif.latex?C\sum_{k=1}^\infty{k^{-\gamma}}=1 "C\sum_{k=1}^\infty{k^{-\gamma}}=1"
[C=\frac{1}{\sum_{k=1}^\infty{k^{\gamma}}}=\frac{1}{\zeta(\gamma)}]: https://latex.codecogs.com/gif.latex?C=\frac{1}{\sum_{k=1}^\infty{k^{\gamma}}}=\frac{1}{\zeta(\gamma)} "eq.4.7"
[\zeta(\gamma)]: https://latex.codecogs.com/gif.latex?\zeta(\gamma) "\zeta(\gamma)"
[p_k=\frac{k^{-\gamma}}{\zeta(\gamma)}]: https://latex.codecogs.com/gif.latex?p_k=\frac{k^{-\gamma}}{\zeta(\gamma)} "eq.4.8"


<style type="text/css">
	img{width: 51%; float: right;}
</style>