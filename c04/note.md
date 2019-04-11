<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c04
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-28 19:54:5
Modified: 	2019-04-11 15:58:32
-----
Copyright (c) 2019 shumez
-->

# 04. The Scale-Free Property

## Contents

* [04.01. Introduction](#0401_introduction)
* [04.02. Power Laws and Scale-Free Networks](#0402_power_laws_and_scale_free_networks)
    * [04.02.01. Discrete Formalism](#040201_discrete_formalism)
    * [04.02.02. Continuum Formalism](#040202_continuum_formalism)


## 04.01. Introduction

[![fig.4.1][fig_04_01]][fig_04_01]

**scale-free network**

## 04.02 Power Laws and Scale-Free Networks

\[p_k \sim k^{-\gamma} \tag{4.1} \]

**power law dist** 

**degree exponent** \(\gamma\)

\[\log{p_k} \sim - \gamma \log{k} \tag{4.2}\]

\(\log{p_k}\) depends linealy on \(\log{k}\)


out-degree \(k_{out}\), in-degree \(k_{in}\)

\[p_{k_{in}} \sim k^{- \gamma_{in}} \tag{4.3}\]

\[p_{k_{out}} \sim k^{- \gamma_{out}} \tag{4.4}\]

\(\gamma_{in}\) and \(\gamma_{out}\)

e.g., \(\gamma_{in} \approx 2.1\), \(\gamma_{out} \approx 2.45\)


**scale-free** ([Barabási, A.L., Albert R., 1999][1999AlbertR_BarabásiAL]) defined as:

A scale-free network is a network whose **degree distribution follows a power law**


### 04.02.01. Discrete Formalism

prob \(p_k\), \(k\) links

\[p_k = C k^{- \gamma} \tag{4.5}\]

constant \(C\) is determined by the normalization cond

\[\sum_{k=1}^\infty {p_k} = 1 \tag{4.6}\]

\[C \sum_{k=1}^\infty {k^{- \gamma}} = 1\]

hence

\[C = \frac{1}{\sum_{k=1}^\infty {k^{\gamma}}} = \frac{1}{\zeta(\gamma)} \tag{4.7}\]

**Riemann-zeta fn** \(\zeta(\gamma)\)

\[p_k = \frac{k^{- \gamma}}{\zeta(\gamma)} \tag{4.8}\]


### 04.02.02. Continuum Formalism







## 

<!-- link -->
[1999AlbertR_BarabásiAL]: https://arxiv.org/pdf/cond-mat/9910332.pdf%3Forigin%3Dpublication_detail "Barabási, A.L. and Albert, R., 1999. Emergence of scaling in random networks. science, 286(5439), pp.509-512."


<!-- figure -->
[fig_04_01]: http://networksciencebook.com/images/ch-04/figure-4-1.jpg "Fig.4.1 The Topology of the World Wide Web"


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


<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->