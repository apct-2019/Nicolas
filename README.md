# Filtros
Objetivo desses filtros é:
- Realizar a filtragem inicial, mantendo apenas a faixa de interesse do rádio, com um baixa perda de inserção (RF filter)
- Executar uma segunda filtragem a fim de manter apenas o espectro de interesse do canal (IF Filter).

![Ilustração do objetivo da filtragem no projeto](objetivo.PNG)


### Especificações 

- Range de frequência (faixa passante do primeiro filtro) : 108 a 136,9917 MHz
- Espaçamento entre os canais : 8.33 ou 25 KHz (seletividade de 60dB)
- Largura de banda do canal: 3 ou 7,5 KHz (seletividade de 6dB)
- FI em 455 KHz
- Impedância: 50 Ohm

## Primeiro filtro

Filtro passivo, do tipo chebyshev. Este filtro foi escolhido como passivo pois deve ser capaz de atuar em potências relativamente altas, já que, ele deve filtrar sinais de alto potência fora da faixa de operação de rádio. Deve ter baixa perda de inserção pois está no início do circuito, o que representa uma atenuação maior no sinal resultante. Além disso não precisa ser extremamente seletivo porque ocorrerá ainda uma segunda filtragem, sua principal função é retirar sinais de alta potência que não são de interesse a fim de evitar a saturação dos componentes posteriores do circuito (blocos de ganho, atenuadores, mixers etc).

![Circuito do Primeiro Filtro](wideBandFilter_circuit.PNG)

![Plot Primeiro Filtro](wideBandFilter_plot.png)

![Plot Primeiro Filtro](wideBandFilter_plot2.png)

#### Componentes do filtro:

- 2 INDUTORES FIXOS CER 0805 18nH 2% 0,6A COILCRAFT 0805CS-180
- INDUTOR FIXO CER 0805 270nH 5% 0,35A COILCRAFT 0805CS-271XJL
- 2 CAPACITORES CER 0402 100PF 50V 1% GRM1555C1H101FA01D
- CAPACITOR CER 0805 6,2pF 250V C0G ±0,1pF 600F6R2BT250XT

## Segundo filtro

Filtro cerâmico, já que a potência de entrada é controlada pelo resto do circuito. Com alta seletividade, centrado em 455KHz. Haverá uma chave de RF para alternar entre os filtros, definindo assim a largura do canal. O filtro abaixo foi escolhido pois atende as nossas especificações, é pequeno e não necessita de circuito externo nem alimentação.

![Filtros escolhidos](filterdatasheet.PNG)

![Resposta em freqência dos filtros](filter.PNG)

![Pin Out do componente](pinout.PNG)
