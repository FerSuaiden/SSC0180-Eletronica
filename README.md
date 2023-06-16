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


### Circuito FALSTAD
O circuito abaixo representa um esquema simplificado da Fonte de Tensão Regulável. Por meio desse mecanismo, foi possível prever o comportamento de cada um dos componentes eletrônicos no circuito e evitar erros de forma geral.

![Circuito FALSTAD](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/148d2203-fdfb-4428-b72e-a01672b71af1)

[Link do Circuito](https://tinyurl.com/2yulsxj7)

### Circuito PCB no EAGLE

O circuito PCB diminui o preço de um protótipo pode ser dimensionado de acordo com a necessidade, permitindo a maior compactação dos componentes eletrônicos. Possui canais elétricos isolados e conexões com encaixes específicos para cada elemento do circuito. 

![Captura de Tela (1)](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/4b198063-e266-4c4b-8409-ad796c55a793)

Essas conexões permitem o encaixe e a solda dos terminais diretamente na placa, o que garante o contato entre os caminhos elétricos e cada terminal.

![Captura de Tela (2)](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/5c528526-ab55-4e2a-8ff7-71635c8ce76d)

Drive do PCB: https://drive.google.com/drive/folders/139w-AAhYZd-ccR1MyaJhjyOBQUGBD-Xi)

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
| 1     | [LED Vermelho](https://www.baudaeletronica.com.br/led-difuso-5mm-vermelho.html)       | Tensão de 2V e Corrente 20mA      | R$ 0,24    |
| 1     | [Transistor](https://www.baudaeletronica.com.br/transistor-npn-bc337.html)       |  Transistor NPN - BC337      | R$ 0,36   |

Valor Total: R$ 39,03

### Referências Bibliográficas

### Resposáveis
- Felipe da Costa Coqueiro
- Fernando Alee Suaiden
- Guilherme Torquato
