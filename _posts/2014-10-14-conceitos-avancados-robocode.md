---
layout: post
title:  "Conceitos técnicos de Robocode"
date:   2014-10-14 13:30:00
categories: tutorial
---

Depois dos conceitos básicos sobre o robocode, descritos [neste post][post], vamos aprofundar mais o estudo da plataforma nesta postagem.

Pra início de conversa, toda classe criada para ser um robô deve extender a classe Robot, do pacote robocode.Robot.
A classe Robot tem vários métodos abstratos, que podem ser chamados para executar uma ação, ou sobreescritos quando você deseja tratar alguma ação.
Alguns métodos são usados para configurar o seu robô, outros, são chamados quando determinado evento acontece.

Os principais eventos para a execução de uma ação são:

* setColors(Color bodyColor, Color gunColor, Color radarColor) - Muda respectivamente a cor do corpo, arma e radar do robô;

* ahead(double pixels) - Move o robo para frente uma quantidade X de pixels;

* back(double pixels) – Move o robo para trás uma quantidade X de pixels;
    
* turnRight(double degree) – Gira o robô para a direita;

* turnLeft(double degree) – Gira o robô para a esquerda;

* turnGunRight(double degree) – Gira a arma para a direita;

* turnGunLeft(double degree) – Gira a arma para a esquerda;

* turnRadarRight(double degree) – Gira o radar para a direita;

* turnRadarLeft(double degree) – Gira o radar para a esquerda;

* fire(double power) : Dispara o canhão com a en

* getBattleFieldWidth() : Obtém a largura (em píxels) do campo de batalha;

* getBattleFieldHeight() : Obtém a altura (em píxels) do campo de batalha;

* getX() : Obtém a coordenada “x” do robô:

* getY() : Obtém a coordenada “y” do robô;

* getHeading(): Obtém a direção do robô em graus;

* getGunHeading(): Obtém a direção da arma em graus;

* getRadarHeading(): Obtém a direção do radar em graus;

* getDistance(): Obtém a distância do oponente em pixels.

* getBearing(): Obtém o ângulo do oponente em relação a você.

Os principais eventos para tratamento de uma ação são:

* run() : Principal método a ser sobrecarregado, é o método chamado quando o robô é iniciado; Ex:

      @Override
      public void run(){
        setColors(Color.blue,Color.yellow, Color.red);
      }

* onScannedRobot(ScannedRobotEvent e) : Método chamado quando um robô é escaneado; Ex:

      @Override
      public void onScannedRobot(ScannedRobotEvent e) {
        double distance = e.getDistance();
        double power = distance >= 50 ? 2 : 1;
        fire( power );
      }

* onHitByBullet(HitByBulletEvent E) : Método chamado quando seu robô é atingido por um tiro; Ex:

      @Override
      public void onHitByBullet(HitByBulletEvent e) {
        back(10);
      }

* onHitWall(HitWallEvent e) : Método chamado quando seu robô atinge uma parede do campo de batalha; Ex:

      @Override
      public void onHitWall(HitWallEvent e) {
        back(20);
      }

Obs: dentro do método run(), deve ser criado um loop infinito, que será sempre executado pelo robô. Ex:
      
      @Override
      public void run(){
        setColors(Color.blue,Color.yellow, Color.red);
        //Loop infinito do robô
        while(true) {
          turnRight(180);
          ahead(100);
          turnGunRight(90);
          back(100);
          turnGunRight(90);
        }
      }

Com essas informações, você ja pode criar um bom robô para a competição de robocode.

[post]: http://robocodeunipar2014.github.io/tutorial/2014/10/08/conceitos-basicos-robocode/
