# SSC0180-Eletronica
## Projeto: Fonte de Tensão Regulável 3v-12v (100mA)
O projeto foi desenvolvido com o objetivo de construir uma fonte de tensão ajustável que funciona no regime de corrente contínua (DC) de 100mA.
### Esquema de Funcionamento
Segue abaixo o esquema do princípio de funcionamento da fonte de tensão: 

![Diagrama de Blocos](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/955e2f46-ec82-4135-9dd8-f7ecabe35f7b)

- Transformador : Transforma a tensão e a corrente elétrica AC para um valor utilizável e positivo em AC
- Retificação: Retifica os pulsos de modo a produzir uma saída polarizada DC.
- Filtragem: Filtra a tensão tornando a corrente contínua.
- Regulação de Tensão: Regula a saída de modo a ter uma tensão constante.

### Teoria

Tensão Alternada: É um tipo de tensão elétrica que varia em amplitude e polaridade ao longo do tempo. A medida é em volts (V) e sua frequência é medida em Hertz (Hz). No Brasil, a frequência padrão da tensão alternada é de 60 Hz. Nesse sentido, podemos dizer que o formato de onda da tensão alternada é descrito pela função f(t) = A.sen(ω.t+θ), onde:

A: amplitude

ω: frequência angular

θ: ângulo de defasagem da onda

t: tempo



### Circuito FALSTAD
O circuito abaixo representa um esquema simplificado da Fonte de Tensão Regulável. Por meio desse mecanismo, foi possível prever o comportamento de cada um dos componentes eletrônicos no circuito e evitar erros de forma geral.

![Circuito FALSTAD](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/148d2203-fdfb-4428-b72e-a01672b71af1)

[Link do Circuito](https://tinyurl.com/2yulsxj7)

### Circuito PCB no EAGLE

O circuito PCB diminui o preço de um protótipo pode ser dimensionado de acordo com a necessidade, permitindo a maior compactação dos componentes eletrônicos. Possui canais elétricos isolados e conexões com encaixes específicos para cada elemento do circuito. 

![Captura de Tela (1)](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/4b198063-e266-4c4b-8409-ad796c55a793)

Essas conexões permitem o encaixe e a solda dos terminais diretamente na placa, o que garante o contato entre os caminhos elétricos e cada terminal.

![Captura de Tela (2)](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/5c528526-ab55-4e2a-8ff7-71635c8ce76d)

[Drive do PCB](https://drive.google.com/drive/folders/139w-AAhYZd-ccR1MyaJhjyOBQUGBD-Xi)

### Componentes Eletrônicos
| Quantidade     | Componentes | Especificações | Valor |
| ---      | ---       | ---      | ---     |
| 1 | [Transformador Bivolt](https://produto.mercadolivre.com.br/MLB-2601528464-transformador-trafo-1212v-500ma-bivolt-_JM)  | 12V/24V     |  R$ 28,99   |
| 1 |[Ponte Retificadora](https://www.baudaeletronica.com.br/ponte-retificadora-kbpc1010.html)| KBPC1010 | R$ 4,90 |
| 1     | [Capacitor](https://www.baudaeletronica.com.br/capacitor-eletrolitico-470uf-25v.html)        | 470uF / 25V     | R$ 0,55  |
| 1     | [Potenciômetro](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html)        | Resistência: 5K  | R$ 2,21    |
| 1     | [Resistor 1k](https://www.baudaeletronica.com.br/resistor-1k-5-1-4w.html)       | 1000 Ω     | R$ 0,05    |
| 1     | [Resistor 2k](https://www.baudaeletronica.com.br/produto/resistor-2k0-5-12w.html)     | 2000 Ω 1/2W    | R$ 0,15   |
| 1     | [Resistor 2k](https://www.baudaeletronica.com.br/produto/resistor-2k-5-18w.html)     | 2000 Ω 1/8W    | R$ 0,05   |
| 1     | [Diodo Zener](https://www.baudaeletronica.com.br/diodo-zener-bzx55c-13v-0-5w.html)       | Diodo Zener BZX55C 13V/0,5W     |  R$ 0,08   |
| 1     | [Fusível de Pico](https://www.baudaeletronica.com.br/produto/pico-fusivel-1a-8mm.html)     |  1 A     | R$ 1,45    |
| 1     | [LED Vermelho](https://www.baudaeletronica.com.br/led-difuso-5mm-vermelho.html)       | 2V/20mA      | R$ 0,24    |
| 1     | [Transistor](https://www.baudaeletronica.com.br/transistor-npn-bc337.html)       |  Transistor NPN - BC337      | R$ 0,36   |

Valor Total: R$ 39,03

### Função dos Componentes

- Transformador: Transforma a tensão alternada da tomada, que possui RMS (root mean square) de 179,6 V, para um valor menor. O seu funcionamento se dá a partir de duas bobinas e a interação entre os seus campos magnéticos, controlando a corrente e a tensão para um valor desejado.

- Diodos: São usados para retificar a corrente alternada. São componentes usados na ponte de diodo que retifica a dupla onda e otimiza a voltagem da tomada através da inversão de um dos semiciclos da função da tensão alternada.

- Capacitor: Armazena a carga durante os picos da corrente alternada, liberando corrente quando a tensão do capacitor é maior que a tensão da fonte.

- Diodo Zener: Conduz corrente elétrica apenas quando a tensão estiver acima da tensão máxima, dessa forma, é possível regular a tensão máxima no circuito.

- Resistores: Limitam a corrente que passam pelos componentes e dissipam calor do circuito.

- Potenciômetro: É um resistor com resistência variável. É utilizado para ajustar a tensão que vai para o transistor.

- Transistor: Utilizado para limitar a passagem de corrente diretamente para a saída.

### Referências Bibliográficas

### Resposáveis
- Felipe da Costa Coqueiro
- Fernando Alee Suaiden
- Guilherme Torquato
- Adhemar
