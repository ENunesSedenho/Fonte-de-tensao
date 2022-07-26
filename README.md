# Trabalho 1 - Fonte de tensão regulável
Projeto da disciplina de Eletrônica para Computação, ministrada pelo Professor Eduardo Simões - USP São Carlos, ICMC. O objetivo é projetar e construir uma fonte de tensão retificadora regulável entre 3V e 12V, com capacidade de 100 mA, com ripple de 10%. A fonte receberá da tomada uma corrente alternada, com frequência de 60Hz, e uma tensão de 127V.

## Grupo 44
|  Nº USP  |  Aluno  |
|---|---|
| 13671810 | Enzo Nunes Sedenho | 
| 13782369 | Luis Henrique Giorgetti Dantas | 
| 13672766 | Pedro Augusto Monteiro Delgado | 
| 13677239 | Yvin Miguel Juanico Carvalho | 

# Componentes da fonte
|  Qtd.  |  Componente |  Preço  |
|---|---|---|
| 1x | Potenciômetro linear 5k Ω | R$ 7,00 |
| 1x | Diodo Zener 13V 1N4743 | R$ 0,48 |
| 1x | Capacitor 560µF 25V | R$ 1,40 |
| 1x | Transistor NPN BC548B| R$ 0,50 |
| 4x | Diodo Retificador 0,7V 1N4007 | R$ 0,20 |
| 2x | Resistor 1k Ω| R$ 0,07 |
| 1x | Resistor 1,5k Ω | R$ 0,07 |
| 1x | Led difuso Vermelho | R$ 0,50 |
| 1x | Protoboard | - | - |
| Total | - | R$ 10,89 |

_Obs.: O transformador, os fios e a protoboard foram emprestados do laboratório._
 
# Diagramas da Fonte

## Circuito no Falstad
> [Diagrama do circuito no simulador Falstad](https://tinyurl.com/29mso46y)
<img src="https://i.imgur.com/h2QQSWN.png">

## Circuito no Eagle
> Diagrama esquemático do circuito no programa Eagle
<img src="https://i.imgur.com/49QObXO.jpg"> 

## PCB no Eagle
> Diagrama PCB do circuito no programa Eagle
<img src="https://i.imgur.com/gJSqxAC.jpg">

# Fotos do circuito montado
> Visão geral do circuito
<img src="https://i.imgur.com/Ky8oyaa.jpg">

> Tensão mínima fornecida pelo circuito
<img src="https://i.imgur.com/XeoWRnE.jpg">

> Tensão máxima fornecida pelo circuito
<img src="https://i.imgur.com/J0DqqGh.jpg">

# Explicação dos componentes
Cada componente possui uma função importante para o bom funcionamento do circuito segundo as especificações buscadas. O objetivo do circuito é receber uma corrente alternada da tomada, com tensão de 127V e fornecer uma tensão regulável entre 3V e 12V, com corrente contínua com capacidade de 100mA. Temos uma fonte de alimentação que simula uma tomada convencional. A corrente fornecida é alternada e possui frequência de 60 hz. A tensão média é de 127 V, o que representa uma tensão de pico de aproximadamente 180 V. 

## Transformador
Para diminuir essa tensão, utilizamos um transformador que, basicamente, transforma a tensão vinda da tomada, com pico de 180V, para uma tensão menor, com pico de aproximadamente 25,4 V. Isso representa uma razão de transformação igual a 7. 

## Ponte de diodos
Após diminuir a tensão utilizando o transformador, a corrente do circuito permanece alternada, sendo ora positiva, ora negativa. Contudo, para o objetivo do circuito, que é fornecer energia para um dispositivo, é necessário que ela seja contínua. Para isso, primeiro, utilizamos uma ponte de diodos.  Após a ponte de diodos, a corrente é sempre positiva, mas possui alta variação, o que não é interessante para o objetivo do circuito. Além disso, a ponte de diodos é responsável por provocar uma queda de tensão do circuito e torná-la mais constante, mas ainda com um “ripple”.

## Capacitor
Utilizando um capacitor, podemos atenuar essa variação de corrente, já que ele será carregado quando a corrente de alimentação estiver aumentando e descarregado quando a corrente de alimentação estiver diminuindo, fornecendo corrente para o restante do circuito. Dessa forma, garantimos uma corrente mais estável para o restante do circuito.

## Diodo Zener
Para controlar a tensão do circuito, utilizamos um diodo zener com tensão de regulagem igual a 13V. O diodo zener só permite a passagem de corrente através dele se a tensão for maior que a tensão de ruptura do diodo, que nesse caso é de 13V. Para qualquer tensão maior que 13V, o diodo zener funciona como um curto-circuito e a corrente passa pelo diodo zener, diminuindo a tensão até 13V, quando o zener não permite mais a passagem de corrente. Dessa forma, a tensão fornecida para o restante do circuito será constante e bem próxima de 13V. É importante adicionar um resistor, nesse caso de 1kΩ, antes do diodo zener, para reduzir a amperagem da corrente e evitar que o diodo zener queime.

## Potenciômetro
Como o objetivo do circuito é fornecer uma tensão regulável de 3V a 12V precisamos que a tensão - nesse ponto do circuito, igual a 13V - possa variar nesse intervalo. Para isso, utilizamos um potenciômetro, que é basicamente um resistor de resistência variável. Nesse caso, o potenciômetro varia de 0Ω a 5kΩ.  Utilizamos um resistor de 1,5kΩ após o potênciometro, que limita o mínimo de tensão que será fornecida pelo circuito, nesse caso, pouco abaixo de 3V. 

## Transistor
O último componente do circuito é o transistor, que regula a corrente com base na variação de tensão entre a base e o emissor, nesse caso, a variação máxima é 0,7 V. O resistor de 120Ω simula o dispositivo que será carregado pela fonte.

## Led
O led funciona exclusivamente para verificar a passagem de corrente no circuito. Utilizamos um resistor de 1kΩ para evitar que o led se queime.

# Cálculos
> Cálculos realizados para projetar o circuito
<img src="https://i.imgur.com/K7KXgve.png">

> [Vídeo explicativo sobre o projeto](https://youtu.be/uK48WSZexMw)
