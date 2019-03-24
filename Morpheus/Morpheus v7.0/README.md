# VERSÃO 2019 PLACA CONTROLADORA
Atualização do driver para o ano de 2019, conforme definido em reunião. Abaixo os detalhes de operação desta placa.

### 1.COMPONENTES E LIMITES DE OPERAÇÃO
A placa possui um medidor de corrente, que impede a elevação desta e consequentes danos ao circuito. No entanto, não possui blocos de alimentação, devendo ser observado:
Possui nessa versão leds que indicam a entrada de PWM nos IN_1 e IN_2, bem como leds indicativos de alimentação nas vias *Bat5S* e *Vcc*.

- Tensão máxima em Bat5S (tensão sobre a ponte H): ~50v (limitado pelos mosfets e pelo motor)
- Tensão máxima em Vcc (tensão de alimentação dos IR2184): entre 10-20v (recomendado usar 12v a 15v).

### 2.CONEXÕES
 O layout foi feito de forma a permitir mais possibilidades de acoplamento da placa à CB (Carrier Board), de forma que conta com 3 pinos de GND de potência, e 1 Bat5S (polo positivo da bateria). Há também dois conectores de flat cable, bastando escolher qual soldar no momento da feitura da placa. Foram postos dois no projeto visualizando também maior número de possibilidades.

![Pinos](https://github.com/roboime/BattleBot-HardwareBoards/blob/master/Morpheus/Morpheus%20v7.0/pinout.png)

### 3.PINOUT
*conector flat J1: - pins 1 a 8: GND
		   - pin 9: saida analogic INA169
	           - pin 10: +3.3v
		   - pin 11: IN_1
	           - pin 12: pino sem conecxão
 		   - pin 13 a 14: Vcc
		   - pin 15: pino sem conecxão
		   - pin 16: IN_2

*conector flat J2: - pins 1 a 4: GND
		   - pin 5: IN_2
		   - pins 6 a 7: GND
	           - pin 8: pino sem conecxão
	           - pin 9 a 10: Vcc
 		   - pin 11: pino sem conecxão
		   - pins 12 a 13: GND
		   - pin 14: IN_1
		   - pin 15: +3.3v
		   - pin 16: saida analogic INA169

### 3.FUNCIONAMENTO
Para fazer o circuito funcionar, certifique-se de que a bateria está ligada, bem como a trilha de *Vcc* está energizada com os valores de tenão apropriados, ditos anteriormente.
Caso utilize o feedback de corrente proporcionado pelo INA169, garanta que a trilha de +3.3v também esteja energizada.

- Giro à esquerda: aplique PWM em IN_1 e 0 em IN_2
- Giro à direita: aplique PWM em IN_2 e 0 em IN_1

OBS.: Recomenda-se utilizar frequência por volta de 20khz, a fim de um obter uma rotação mais suavizada do motor, segundo testes feitos previamente com o motor Integy 65T, do SanhAÇO.

### 4.Testes
Recomenda-se testar o circuito ligado a uma *fonte de tensão* e não à bateria, para se evitar curto-circuitos na bateria, o que pode danificá-la. Para isso, utilize 14v como tensão de testes, limitando a corrente em 1.5A, caso utilize o motor sem carga (eixo rodando sem esforço).
Observe sempre os 4 leds indicativos das placas para rápida identificação de possíveis problemas.