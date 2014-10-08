---
layout: post
title:  "Conceitos básicos de Robocode"
date:   2014-10-08 10:25:11
categories: tutorial
---
Robocode é um projeto educacional open source, que visa o ensino da linguagem Java (ou .Net) e orientação a objetos.
Os robôs são criados a partir da definição do seu comportamento em métodos sobrecarregados, chamados quando determinados eventos ocorrem.

A programação dos robôs pode ser feita utilizando qualquer editor de texto, sendo que existem maneiras de integra-lo com o Eclipse e NetBeans, além de ele possuir um editor próprio.

###Anatomia de um robô

![Anatomia de um robô](/assets/anatomia_robo.jpg)

* Corpo (body) – Permite o movimento para frente e para trás.
* Arma (gun) – Permite atirar um projétil.
* Radar – Utilizado para identificar outros robôs no campo de batalha.

Cada uma das partes de um robô pode ser girado 360° individualmente, ou em grupos.

###Conceitos e terminologias básicas

* Cooling rate – Tempo em que a arma está superaquecida e não pode atirar. Esse tempo será definido em 0.1 segundos nas batalhas que ocorrerão.
* Sistema Métrico – O sistema métrico é em pixels, e considerada a origem(0,0) como o canto inferior esquerda da tela.
* Projéteis - Você usa sua energia como tiro.
* Um robô é eliminado quando sua energia chega a 0.
