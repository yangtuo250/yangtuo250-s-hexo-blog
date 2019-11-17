---
title: statistics1
date: 2019-11-10 15:17:43
category: Statistics
tags: [statistics, math]
---
- [Problem 1 松鼠、熊与下雪](#problem-1-%e6%9d%be%e9%bc%a0%e7%86%8a%e4%b8%8e%e4%b8%8b%e9%9b%aa)
  - [1. 对于E山，有如下事实：](#1-%e5%af%b9%e4%ba%8ee%e5%b1%b1%e6%9c%89%e5%a6%82%e4%b8%8b%e4%ba%8b%e5%ae%9e)
  - [&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$P(发现熊|下雪)<P(发现松鼠|下雪)$](#nbspnbspnbspnbspnbspnbspnbspnbspnbspnbspp%e5%8f%91%e7%8e%b0%e7%86%8a%e4%b8%8b%e9%9b%aap%e5%8f%91%e7%8e%b0%e6%9d%be%e9%bc%a0%e4%b8%8b%e9%9b%aa)
  - [&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$P(发现熊|不下雪)<P(发现松鼠|不下雪)$](#nbspnbspnbspnbspnbspnbspnbspnbspnbspnbspp%e5%8f%91%e7%8e%b0%e7%86%8a%e4%b8%8d%e4%b8%8b%e9%9b%aap%e5%8f%91%e7%8e%b0%e6%9d%be%e9%bc%a0%e4%b8%8d%e4%b8%8b%e9%9b%aa)
  - [试问能否断言E山的$P(发现熊)<P(发现松鼠)$？](#%e8%af%95%e9%97%ae%e8%83%bd%e5%90%a6%e6%96%ad%e8%a8%80e%e5%b1%b1%e7%9a%84p%e5%8f%91%e7%8e%b0%e7%86%8ap%e5%8f%91%e7%8e%b0%e6%9d%be%e9%bc%a0)
  - [2. 与D山相比，C山的$P(发现松鼠|下雪)$更高。同时，$P(发现松鼠|不下雪)$也是C山更高。试问能否断言C山的$P(发现松鼠)$更高？](#2-%e4%b8%8ed%e5%b1%b1%e7%9b%b8%e6%af%94c%e5%b1%b1%e7%9a%84p%e5%8f%91%e7%8e%b0%e6%9d%be%e9%bc%a0%e4%b8%8b%e9%9b%aa%e6%9b%b4%e9%ab%98%e5%90%8c%e6%97%b6p%e5%8f%91%e7%8e%b0%e6%9d%be%e9%bc%a0%e4%b8%8d%e4%b8%8b%e9%9b%aa%e4%b9%9f%e6%98%afc%e5%b1%b1%e6%9b%b4%e9%ab%98%e8%af%95%e9%97%ae%e8%83%bd%e5%90%a6%e6%96%ad%e8%a8%80c%e5%b1%b1%e7%9a%84p%e5%8f%91%e7%8e%b0%e6%9d%be%e9%bc%a0%e6%9b%b4%e9%ab%98)
<!-- more -->

## Problem 1 松鼠、熊与下雪

### 1. 对于E山，有如下事实：

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$P(发现熊|下雪)<P(发现松鼠|下雪)$  

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$P(发现熊|不下雪)<P(发现松鼠|不下雪)$

### 试问能否断言E山的$P(发现熊)<P(发现松鼠)$？

能!

$$P(下雪)+P(不下雪)=1$$

$$P(发现熊,下雪)+P(发现熊,不下雪)=P(发现熊)$$

$$P(发现熊,下雪)=P(发现熊|下雪)P(下雪)$$

$$P(发现熊)=P(发现熊|下雪)P(下雪)+P(发现熊|不下雪)P(不下雪)$$

松鼠同理

### 2. 与D山相比，C山的$P(发现松鼠|下雪)$更高。同时，$P(发现松鼠|不下雪)$也是C山更高。试问能否断言C山的$P(发现松鼠)$更高？

> 准备知识 辛普森悖论
>> (wikipedia)辛普森悖论（亦称辛普森诡论）  
当人们尝试探究两种变量（比如新生录取率与性别）是否具有相关性的时候，会分别对之进行分组研究。然而，在分组比较中都占优势的一方，在总评中有时反而是失势的一方。该现象于20世纪初就有人讨论，但一直到1951年，E.H.辛普森在他发表的论文中阐述此一现象后，该现象才算正式被描述解释。后来就以他的名字命名此悖论，即辛普森悖论。  
为了避免辛普森悖论的出现，就需要斟酌**各分组的权重**，并乘以一定的系数去消除以分组数据基数差异而造成的影响。同时，我们必需清楚了解情况，以综合考虑是否存在造成此悖论的潜在因素。

证伪：  
||$P(发现松鼠｜下雪)$|$P(发现松鼠｜不下雪)$|$P(下雪)$|$P(发现松鼠)$|
|:-:|:-:|:-:|:-:|:-:|
|C山|0.9|0.1|0.01|$0.9\times0.01+0.1\times0.99=0.108$|
|D山|0.5|0|0.99|$0.5\times0.99+0\times0.01=0.495$|

Talk is cheap, show me your formula. 
