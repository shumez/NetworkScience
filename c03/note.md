<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/NetworkScience/c03
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-06 20:27:3
Modified: 	2019-03-06 21:52:52
-----
Copyright (c) 2019 shumez
-->

# 03 Random Networks

## Contents

01. [Introduction](#0301-Introduction)
02. [The Random Network Model](#0302-The-Random-Network-Model)
    * [Box 3-1 Defining Random Networks](#Box-3-1-Defining-Random-Networks)
    * [Box 3-2 Random Networks: a Brief History](#Box-3-2-Random-Networks:-a-Brief-History)
03. [Number of Links](#0303-Number-of-Links)


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


### Box 3-2 Random Networks: a Brief History



## 03.03 Number of Links

[![fig.3.3][fig_03_03]][fig_03_03]

- attempt to \(p^L\)

\[ \begin{pmatrix} \frac{N(N-1)}{2} \\ L \end{pmatrix} \tag{3.0} \]




[fig_03_03]: http://networksciencebook.com/images/ch-03/figure-3-3.jpg "Random Networks are Truly Random"

<style type="text/css">
	img{width: 50%; float: right;}
</style>