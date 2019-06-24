<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/NetworkScience/04
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-28 19:54:5
Modified: 	2019-06-24 15:33:41
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


### Box 04.01. The 80/20 Rule and the Top One Percent

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

\[ \langle k^n \rangle = \sum_{k_{\min}}^\infty{k^n p_k} \approx \int\limits_{k_{\min}}^\infty{k^n p(k)}dk \tag{4.19} \]

lower moments:  

* \(n=1\): 1st moment is average \(\langle k \rangle\)
* \(n=2\): 2nd moment, \(\langle k^2 \rangle\),  
    * calculate variance \(\sigma^2 = \langle k^2 \rangle - \langle k \rangle ^2\)
    * standard deviation \(\sigma\)
* \(n=3\): 3rd moment, \(\langle k^3 \rangle\), determine **[skewness]** of distribution: how symmetric is \(p_k\) around the average \(\langle k \rangle\)

for scale-free network 

\[ \langle k^n \rangle = \int\limits_{k_{\min}}^{k_{\max}}{k^n p(k) dk} = C \frac{k_{\max}^{n - \gamma + 1} - k_{\min}^{n - \gamma + 1}}{n - \gamma + 1} \tag{4.20} \]

while \(k_{\min}\) is fixed, \(k_{\max}\) increases w the system size  
\(k_{\max} \to \infty\)

* if \(n - \gamma + 1 ≤ 0 \), \(k_{\max}^{n - \gamma + 1} \to 0\), \(\langle k^n \rangle \to \text{finite}\)
* if \(n - \gamma + 1> 0\), \(\langle k^n \rangle \to \infty\)

many scale-free netw \(\gamma \in (2,3)\),  
\(\langle k \rangle \to \text{finite}\), \(\langle k^2 \rangle, \langle k^3 \rangle \to \infty\)

* **Random netw have a scale**

\(\sigma_k = \langle k \rangle^{\frac{1}{2}}\)

in range \(k = \langle k \rangle \pm \langle k \rangle^{\frac{1}{2}}\)

* **Scale-free netw lack a scale** 

power-law degreee dist w \(\gamma < 3\)   
1st moment: finite  
2nd moment: infinite

e.g., WWW sample  
\(\langle k \rangle = 4.60\), \(\gamma\approx2.1\)

[![Fig.4.7][fig0407]][fig0407]

[![Fig.4.8][fig0408]][fig0408]


## [04.05. Universality][4.5]

[![Fig.4.9][fig0409]][fig0409]

[![Fig.4.10][fig0410]][fig0410]


### 04.05.01. Plotting the Degree Distribution

log-log plot

[05.14. ADVANCED TOPICS 4.B](../05/#0514_advanced_topic_4b_nonlinear_preferential_attachment)

### 04.05.02. Measuring the Degree Exponent

[ADVANCED TOPICS 4.C][]

### 04.05.03. The Shape of \(p_k\) for Real Networks



### Box 04.02. Timeline: Scale-Free Networks
### Box 04.03. Not All Network Are Scale-Free
## 04.06. Ultra-Small Property
### 04.06.01. Anomalous Regime (γ = 2)
### 04.06.02. Ultra-Small World (2 ‹ γ ‹ 3)
### 04.06.03. Critical Point (γ = 3)
### 04.06.04. Small World (γ > 3)
### Box 04.04. We Are Always Close to the Hubs
## 04.07. The Role of the Degree Exponent
### Box 04.05. The γ Dependent Properties of Scale-Free Networks
### 04.07.01. Anomalous Regime (γ ≤ 2)
### 04.07.02. Scale-Free Regime (2 < γ < 3)
### 04.07.03. Random Network Regime (γ < 3)
### Box 04.06. Why Scale-Free Networks With γ < 2 Do Not Exist
## 04.08. Generating Networks with Arbitrary Degree Distribution
### 04.08.01. Configuration Model
### Box 04.07. Generating a Degree Sequence with Power-Law Distribution
### 04.08.02. Degree-Preserving Randomization
### 04.08.03. Hidden Parameter Model
### Box 04.08. Testing the Small-Word Property
## 04.09. Summary
### 04.09.01. Exponentially Bounded Networks
### 04.09.02. Fat Tailed Networks
### Box 04.09. At a Glance: Scale-Free Networks
## 04.10. Homework
## 04.11. Advanced Topic 3.A Power Laws
### 04.11.01. Exponentially Bounded Distributions
### 04.11.02. Fat Tailed Distributions
### 04.11.03. Crossover Distribution (Log-Normal, Stretched Exponential)
### Box 04.10. Degree Distribution of Real Networks
## 04.12. Advanced Topic 3.B Plotting Power-laws
### 04.12.01. Use a Log-Log Plot
### 04.12.02. Avoid Linear Binning
### 04.12.03. Use Logarithmic Binning
### 04.12.04. Use Cumulative Distribution
## 04.13. Advanced Topic 3.C Estimating the Degree Exponent
### 04.13.01. Fitting Procedure
### 04.13.02. Goodness-of-fit
### 04.13.03. Fitting Real Distributions
### 04.13.04. Systematic Fitting Issues
## 04.14. Bibliography



## 
<!-- toc -->
[04]: http://networksciencebook.com/chapter/4
[0401]: #0401_introduction

[0402]: #0402_power_laws_and_scale-free_networks
[040201]: #040201_discrete_formalism
[040202]: #040202_continuum_formalism
[box0401]: #box_0401_the_8020_rule_and_the_top_one_percent

[0403]: #0403_hubs
[040301]: #040301_the_largest_hub

[0404]: #0404_the_meaning_of_scale-free

[0405]: #0405_universality
[040501]: #040501_plotting_the_degree_distribution
[040502]: #040502_measuring_the_degree_exponent
[040503]: #040503_the_shape_of_p_k_for_real_networks
[box0402]: #box_0402_timeline_scale-free_networks
[box0403]: #box_0403_not_all_network_are_scale-freebox

[0406]: #0406_ultra-small_property
[040601]: #040601_anomalous_regime_2
[040602]: #040602_ultra-small_world_2_3
[040603]: #040603_critical_point_3
[040604]: #040604_small_world_3
[box0404]: #box_0404_we_are_always_close_to_the_hubs

[0407]: #0407_the_role_of_the_degree_exponent
[box0405]: #box_0405_the_dependent_properties_of_scale-free_networks
[040701]: #040701_anomalous_regime_2
[040702]: #040702_scale-free_regime_2_3
[040703]: #040703_random_network_regime_3
[box0406]: #box_0406_why_scale-free_networks_with_2_do_not_exist

[0408]: #0408_generating_networks_with_arbitrary_degree_distribution
[040801]: #040801_configuration_model
[box0407]: #box_0407_generating_a_degree_sequence_with_power-law_distribution
[040802]: #040802_degree-preserving_randomization
[040803]: #040803_hidden_parameter_model
[box0408]: #box_0408_testing_the_small-word_property

[0409]: #0409_summary
[040901]: #040901_exponentially_bounded_networks
[040902]: #040902_fat_tailed_networks
[box0409]: #box_0409_at_a_glance_scale-free_networks

[0410]: #0410_homework

[0411]: #0411_advanced_topic_3a_power_laws
[041101]: #041101_exponentially_bounded_distributions
[041102]: #041102_fat_tailed_distributions
[041103]: #041103_crossover_distribution_log-normal_stretched_exponential
[box0410]: #box_0410_degree_distribution_of_real_networks

[0412]: #0412_advanced_topic_3B_plotting_power-laws
[041201]: #041201_use_a_log-log_plot
[041202]: #041202_avoid_linear_binning
[041203]: #041203_use_logarithmic_binning
[041204]: #041204_use_cumulative_distribution

[0413]: #0413_advanced_topic_3c_estimating_the_degree_exponent
[041301]: #041301_fitting_procedure
[041302]: #041302_goodness-of-fit
[041303]: #041303_fitting_real_distributions
[041304]: #041304_systematic_fitting_issues

[0414]: #0414_bibliography


[4.1]: http://networksciencebook.com/chapter/4#introduction4
[4.2]: http://networksciencebook.com/chapter/4#power-laws
[4.3]: http://networksciencebook.com/chapter/4#hubs
[4.4]: http://networksciencebook.com/chapter/4#scale-free
[4.5]: http://networksciencebook.com/chapter/4#universality


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
[fig0407]: http://networksciencebook.com/images/ch-04/figure-4-7.jpg "Fig.4.7 Lack of an Internal Scale"
[fig0408]: http://networksciencebook.com/images/ch-04/figure-4-8.jpg "Fig.4.8 Standard Deviation is Large in Real Networks"
[fig0409]: http://networksciencebook.com/images/ch-04/figure-4-9.jpg "Fig.4.9 The topology of the Internet"
[fig0410]: http://networksciencebook.com/images/ch-04/figure-4-10.jpg "Fig.4.10 Many Real Networks are Scale-free"

<!-- term -->
[skewness]: #0404 "歪み, 歪度"



<style type="text/css">
	img{width: 51%; float: right;}
</style>