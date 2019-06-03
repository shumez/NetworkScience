<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/NetworkScience/04
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-28 19:54:5
Modified: 	2019-06-03 16:20:45
-----
Copyright (c) 2019 shumez
-->

# [04. The Scale-Free Property][04]

## Contents

* [04.01. Introduction][0401]
* [04.02. Power Laws and Scale-Free Networks][0402]
    * [04.02.01. Discrete Formalism][040201]
    * [04.02.02. Continuum Formalism][040202]
    * [Box 04.01. The 80/20 Rule and the Top One Percent][box0401]
* [04.03. Hubs][0403]
    * [04.03.01. The Largest Hub][040301]
* [04.04. The Meaning of Scale-Free][0404]
* [04.05. Universality][0405]
    * [04.05.01. Plotting the Degree Distribution][040501]
    * [04.05.02. Measuring the Degree Exponent][040502]
    * [04.05.03. The Shape of p~k~ for Real Networks][040503]
    * [Box 04.02. Timeline: Scale-Free Networks][box0402]
    * [Box 04.03. Not All Network Are Scale-Free][box0403]
* [04.06. Ultra-Small Property][0406]
    * [04.06.01. Anomalous Regime (γ = 2)][040601]
    * [04.06.02. Ultra-Small World (2 ‹ γ ‹ 3)][040602]
    * [04.06.03. Critical Point (γ = 3)][040603]
    * [04.06.04. Small World (γ > 3)][040604]
    * [Box 04.04. We Are Always Close to the Hubs][box0404]
* [04.07. The Role of the Degree Exponent][0407]
    * [Box 04.05. The γ Dependent Properties of Scale-Free Networks][box0405]
    * [04.07.01. Anomalous Regime (γ≤ 2)][040701]
    * [04.07.02. Scale-Free Regime (2 ‹ γ ‹ 3)][040702]
    * [04.07.03. Random Network Regime (γ › 3)][040703]
    * [Box 04.06. Why Scale-Free Networks With γ ‹ 2 Do Not Exist][box0406]
* [04.08. Generating Networks with Arbitrary Degree Distribution][0408]
    * [04.08.01. Configuration Model][040801]
    * [Box 04.07. Generating a Degree Sequence with Power-Law Distribution][box0407]
    * [04.08.02. Degree-Preserving Randomization][040802]
    * [04.08.03. Hidden Parameter Model][040803]
    * [Box 04.08. Testing the Small-Word Property][box0408]
* [04.09. Summary][0409]
    * [04.09.01. Exponentially Bounded Networks][040901]
    * [04.09.02. Fat Tailed Networks][040902]
    * [Box 04.09. At a Glance: Scale-Free Networks][box0409]
* [04.10. Homework][0410]
* [04.11. Advanced Topic 3.A Power Laws][0411]
    * [04.11.01. Exponentially Bounded Distributions][041101]
    * [04.11.02. Fat Tailed Distributions][041102]
    * [04.11.03. Crossover Distribution (Log-Normal, Stretched Exponential)][041103]
* [04.12. Advanced Topic 3.B Plotting Power-laws][0412]
    * [04.12.01. Use a Log-Log Plot][041201]
    * [04.12.02. Avoid Linear Binning][041202]
    * [04.12.03. Use Logarithmic Binning][041203]
    * [04.12.04. Use Cumulative Distribution][041204]
    * [Box 04.10. Degree Distribution of Real Networks][box0410]
* [04.13. Advanced Topic 3.C Estimating the Degree Exponent][0413]
    * [04.13.01. Fitting Procedure][041301]
    * [04.13.02. Goodness-of-fit][041302]
    * [04.13.03. Fitting Real Distributions][041303]
    * [04.13.04. Systematic Fitting Issues][041304]
* [04.14. Bibliography][0414]


## [04.01. Introduction][4.1]

[![fig.4.1][fig0401]][fig0401]

scale-free vs. random network

* highly connected; hubs forbidden vs. small-degree, few hubs w/ large number of links

**scale-free network**

## [04.02. Power Laws and Scale-Free Networks][4.2]

[fig.4.2][fig0402] indicates

\[ p_k \sim k^{-\gamma} \tag{4.1} \]

eq.4.1: **power law dist** 

**degree exponent** \(\gamma\)

\[ \log{p_k} \sim - \gamma \log{k} \tag{4.2} \]

\( \log{p_k} \) depends linealy on \( \log{k} \)


[![fig.4.2][fig0402]][fig0402]

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

randamly chosen node has degree \([k_1, k_2]\)


### Box 4-1 The 80/20 Rule and the Top One Percent

<!-- [![fig.4.3][fig_04_03]][fig_04_03] -->

## [04.03. Hubs][4.3]

high-\(k\) region of \(p_k\)

* for small \(k\), power law is above the Poisson fn
* for \(k\) in the vicinity of \(\langle k \rangle\), \(k \approx \langle k \rangle\)
* for large \(k\), 

prob (node with \(k=100\))   
\(p_{100}\approx 10^{-94}\) in Poisson dist  
\(p_{100} \approx 4 \times 10^{-4}\) in power law

if WWW be random network w/ \(\langle k \rangle = 4.6\), size \(N\approx10^{12}\)

\[ N_{k \ge 100} = 10^{12} \sum_{k=100}^\infty{\frac{(4.6)^k}{k!} e^{-4.6}} \simeq 10^{-82} \tag{4.14} \]


[![fig.4.4][fig0404]][fig0404]


### 04.03.01. The Largest Hub

WWW is estimated to be \(N \approx 10^{12}\) nodes  
Earth;s population about \(N \approx 7 \times 10^9\)  
human cell \(N \approx 20000\) genes

maximum degree \(k_{\max}\) **natural cutoff** of the degree dist \(p_k\)

exponential dist

\[ p(k)  = Ce^{- \lambda k} \]

minimum degree \(k_{\min}\) 

\[ \int_{k_{\min}}^\infty{p(k)} \mathrm{d}k = 1 \tag{4.15} \]

&because;

\[ 
    \begin{align*} 
        \int_{k_{\min}}^\infty{C e^{- \lambda k} dk} &= 1 \\
        \Bigg[ - \frac{1}{\lambda} C e^{- \lambda k} \Bigg]_{k_{\min}}^\infty &= 1 \\
        \Bigg( -\frac{1}{\lambda} C e^{- \lambda\times\infty} \Bigg) - \Bigg( -\frac{1}{\lambda} C e^{- \lambda k_{\min}} \Bigg) &= 1 \\
        0 + \frac{1}{\lambda} C e^{- \lambda k_{\min}} &= 1 \\
        \Rightarrow C &= \lambda e^{\lambda k_{\min}}
    \end{align*} 
    \tag{4.15.1}
\]

eq.4.15 provide 
\[ C = \lambda e^{\lambda k_{\min}} \]

\(k_{\max}\) is \(\frac{1}{N}\):

\[ \int_{k_{\min}}^\infty{p(k) \mathrm{d}k} = \frac{1}{N} \tag{4.16} \]

eq.4.16 yields

\[ k_{\max} = k_{\min} + \frac{\ln{N}}{\lambda} \tag{4.17} \]

\(\ln{N}\)


[![fig.4.5][fig0405]][fig0405]

\[ k_{\max} = k_{\min} N^{\frac{1}{\gamma-1}} \tag{4.18} \]

[![Fig.4.6][fig0406]][fig0406]


## [04.04. The Meaning of Scale-Free][4.4]

\(n\)^th^ moment of the degree distribution is def'd as

\[ \langle k^n \rangle = \sum_{k_{\min}}^\infty{k^n p_k} \approx \int_{k_{\min}}^\infty{k^n p(k)}dk \tag{4.19} \]

lower moments:  

* \(n=1\): 1st moment is average \(\langle k \rangle\)
* \(n=2\): 2nd moment, \(\langle k^2 \rangle\),  
    * calculate variance \(\sigma^2 = \langle k^2 \rangle - \langle k \rangle ^2\)
    * standard deviation \(\sigma\)
* \(n=3\): 3rd moment, \(\langle k^3 \rangle\), determine **[skewness]** of distribution: how symmetric is \(p_k\) around the average \(\langle k \rangle\)

for scale-free network 

\[ \langle k^n \rangle = \int_{k_{\min}}^{k_{\max}}{k^n p(k) dk} = C \frac{k_{\max}^{n - \gamma + 1} - k_{\min}^{n - \gamma + 1}}{n - \gamma + 1} \tag{4.20} \]

while \(k_{\min}\) is fixed, \(k_{\max}\) increases w the system size  
\(k_{\max} \to \infty\)

* if \(n - \gamma + 1 ≤ 0 \), \(k_{\max}^{n - \gamma + 1} \to 0\), \(\langle k^n \rangle \to \text{finite}\)
* if \(n - \gamma + 1> 0\), \(\langle k^n \rangle \to \infty\)

many scale-free netw \(\gamma \in (2,3)\),  
\(\langle k \rangle \to \text{finite}\), \(\langle k^2 \rangle, \langle k^3 \rangle \to \infty\)

* **Random netw have a scale**
* **Scale-free netw lack a scale** 


## 04.12. Advanced Topic 3.B Plotting Power-laws

### 04.12.01. Use a Log-Log Plot

### 04.12.02. Avoid Linear Binning

### 04.12.03. Use Logarithmic Binning

### 04.12.04. Use Cumulative Distribution




## 
<!-- toc -->
[04]: http://networksciencebook.com/chapter/4
[0401]: #0401_introduction
[0402]: #0402_power_laws_and_scale-free_networks
[040201]: #040201_discrete_formalism
[040202]: #040202_continuum_formalism
[box0401]: #box_4-1_the_8020_rule_and_the_top_one_percent
[0403]: #0403_hubs
[040301]: #040301_the_largest_hub
[0404]: #0404_the_meaning_of_scale-free

[0412]: #0412_advanced_topic_3B_plotting_power-laws
[041201]: #041201_use_a_log-log_plot
[041202]: #041202_avoid_linear_binning
[041203]: #041203_use_logarithmic_binning
[041204]: #041204_use_cumulative_distribution

[4.1]: http://networksciencebook.com/chapter/4#introduction4
[4.2]: http://networksciencebook.com/chapter/4#power-laws
[4.3]: http://networksciencebook.com/chapter/4#hubs
[4.4]: http://networksciencebook.com/chapter/4#scale-free


<!-- ref -->
[1999AlbertR_BarabásiAL]: https://arxiv.org/pdf/cond-mat/9910332.pdf%3Forigin%3Dpublication_detail "Barabási, A.L. and Albert, R., 1999. Emergence of scaling in random networks. science, 286(5439), pp.509-512."

[Riemann-zeta fn]: https://en.wikipedia.org/wiki/Riemann_zeta_function

<!-- figure -->
[fig0401]: http://networksciencebook.com/images/ch-04/figure-4-1.jpg "Fig.4.1 The Topology of the World Wide Web"
[fig0402]: http://networksciencebook.com/images/ch-04/figure-4-2.jpg "Fig.4.2 The Degree Distribution of the WWW"
[fig0403]: http://networksciencebook.com/images/ch-04/figure-4-3.jpg "Fig.4.3 Vilfredo Federico Damaso Pareto (1848 – 1923) "
[fig0404]: http://networksciencebook.com/images/ch-04/figure-4-4.jpg "Fig.4.4 Poisson vs. Power-law Distributions"
[fig0405]: http://networksciencebook.com/images/ch-04/figure-4-5.jpg "Fig.4.5 Hubs are Large in Scale-free Networks "
[fig0405]: https://raw.githubusercontent.com/shumez/NetworkScience/master/NetworkScience/04/fig/fig0405.png
[fig0406]: http://networksciencebook.com/images/ch-04/figure-4-6.jpg "Fig.4.6 Random vs. Scale-free Networks"

<!-- term -->
[skewness]: #0404 "歪み, 歪度"

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