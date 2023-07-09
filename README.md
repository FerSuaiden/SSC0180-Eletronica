# SSC0180-Eletrônica
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

- **Tensão Alternada:** É um tipo de tensão elétrica que varia em amplitude e polaridade ao longo do tempo. A medida é em volts (V) e sua frequência é medida em Hertz (Hz). No Brasil, a frequência padrão da tensão alternada é de 60 Hz. Nesse sentido, podemos dizer que o formato de onda da tensão alternada é descrito pela função *f(t) = A.sen(ω.t+θ)*, onde:

A: amplitude

ω: frequência angular

θ: ângulo de defasagem da onda

t: tempo

![senoideeew](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/e19a8d9d-73a2-4312-b2a9-4eb518f386b8)

Desse modo, podemos calcular o valor médio da função periódica, tomando θ = 0°: 

$$ V(t) = Vo \times sen(ω \cdot t) $$

Usando a forma infinitesimal para calcular a área embaixo da curva do gráfico:

$$ V(t) = \frac{1}{T} \times \int_{0}^{t} 𝑉𝑚á𝑥 \times 𝑠𝑒𝑛(ω \cdot 𝑡) \ \cdot dt $$

Sabendo que o período da senóide é 𝑇 = 2π/ω, dizemos que:

$$ V(t) = \frac{ω}{2π} \times \int_{0}^{t} 𝑉𝑚á𝑥 \times 𝑠𝑒𝑛(ω \cdot 𝑡) \ \cdot dt $$
                                        
- **Tensão Eficaz:** É a tensão alternada equivalente a uma tensão contínua para que a potência
produzida seja a mesma. Logo, por definição, temos:

$$ Pot_{DC} = \frac{V²}{R} \ (i) $$

$$Pot_{AC} = \frac{V(t)²}{R} \ (ii) $$

Igualando (i) e (ii):

$$ \frac{V²}{R} = \frac{V(t)²}{R} \rightarrow V² = \frac{ω}{2π} \times \int_{0}^{t} [𝑉𝑚á𝑥 \times 𝑠𝑒𝑛(ω \cdot 𝑡) \ \cdot dt ]² $$

$$ \rightarrow V_{rms} = V_{máx} \times \sqrt(\frac{ω}{2π} \times \int_{0}^{t} [𝑠𝑒𝑛(ω \cdot 𝑡) \ \cdot dt ]²) \ (iii) $$

Resolvendo a integral, tem-se:

$$ \int_{0}^{t} [𝑠𝑒𝑛(ω \cdot 𝑡) \,dt ]² = (\frac{t}{2} - \frac{sen(2ω \cdot 𝑡)}{4}) | _ {0}^{T} $$

$$ \rightarrow (\frac{T}{2} - \frac{sen(2ω \cdot T)}{4}) = (\frac{π}{ω} - \frac{sen(4 \cdot π)}{4}) = \frac{π}{ω} \ (iv) $$

Substituindo (iv) em (iii): 

$$ V_{rms} = V_{máx} \times \sqrt(\frac{π}{ω} \times \frac{ω}{2π}) \rightarrow V_{rms} = V_{máx} \times \sqrt\frac{1}{2} $$

Normalmente, as tomadas operam com Vrms = 127 V. Então, para um estudo efetivo da tensão no projeto, podemos calcular a tensão máxima da seguinte maneira:

$$ V_{máx} = 127 \times \sqrt\frac{1}{2} \approx  179,6 V $$

- **Razão do Transformador:** Para trabalhar com uma saída de tensão de Vs = 25,8 V (medido na prática), usamos a equação do transformador:

$$ k = \frac{N_{máx}}{N_{s}} = \frac{V_{máx}}{V_{s}} \rightarrow k = \frac{179,6}{25,8} \approx 6,96 $$

- **Queda de Tensão na Ponte Retificadora:** No circuito haverá sempre dois diodos que estarão sempre em funcionamento (exceto nos momentos de gaps que são abastecidos pelo capacitor). Tais diodos consomem aproximadamente 0,7 V. Logo, haverá uma queda de tensão de 1,4 V na ponte. Então a voltagem que sai para o circuito é:

$$ Vs' = Vs - 1,4 V \rightarrow Vs' = 25,8 V - 1,4 V \rightarrow Vs' = 24,4 V $$

**Cálculo da Capacitância:** 

(i) O filtro capacitivo tem a finalidade de reduzir a variação de tensão e de corrente no caso das altas frequências, eliminando a tensão alternada pulsativa e transformando-a em uma tensão (contínua) que varia menos. Usando a Lei de Coulomb, deduzimos facilmente a expressão que fornece o valor da capacitância:

$$ Q = V \times C = I \times Δt $$

Mas sabemos que: 

$$ Δt = \frac{1}{f} $$

Então:

$$ C = \frac{i_{total}}{f \times V_{ripple}} $$

(ii) Assumindo que queremos um ripple de no máximo 10%: 

$$ V_{ripple} = 0,1 \times Vs’ → Vripple = 0,1 \times 24,4 → V_{ripple} = 2,44 V $$

Dessa forma, podemos calcular as tensões máximas e mínimas de saída no ciclo. Sejam:
- Vmáxs: Tensão máxima de saída
- Vripple: Tensão de ripple
- Vmíns: Tensão mínima de saída

![ripple](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/129008295/cfa6356c-1da2-4800-a43d-4e5527479e99)

Então, usando a fórmula reduzida da tensão de carga no capacitor:

$$ V_{máxs} = Vs’ (1 − \frac{ripple}{2}) → V_{máxs} = 24,4.(1 − \frac{10}{2 \times 100 }) → V_{máxs} = 23,18 V $$

$$ V_{míns} = V_{máxs} - V_{ripple} → V_{míns} = 23,18 - 2,44 → V_{míns} = 20,74 V $$

Nesse sentido, podemos calcular a corrente total no circuito com base nessas informações:

$$ i_{LED} = \frac{V_{máxs}-V_{LED}}{R_{LED}} = \frac{12,1}{4400} \approx 2,75 mA $$

$$ i_{ZENNER} = \frac{V_{máxs}-V_{ZENNER}}{R_{ZENNER}} = \frac{22,18 - 12,9}{2200} \approx 4,22 mA $$

$$ i_{POTENCIÔMETRO} = \frac{V_{máxs}}{R_{POTENCIÔMETRO}} = \frac{22,18}{5000} \approx 4,43 mA $$

$$ i_{TRANSISTOR} = \frac{V_{máxs}}{R_{TRANSISTOR}} = \frac{23,18}{230} \approx 100,07 mA $$

Logo, 

$$ i_{TOTAL} = 2,75 + 4,22 + 4,43 + 100,07 = 112,18 mA $$

Por fim, no cálculo da capacitância usamos f = 120 Hz pois a saída da frequência é o dobro da entrada para uma retificação em onda completa na ponte:

$$ C = \frac{i_{TOTAL}}{f \cdot V_{ripple}} = \frac{112,18 \times 10^{-3}}{120 \times 2,44} \approx 383,12 µF $$

O valor comercial mais próximo do valor teórico é 470µF 50V, optamos por uma margem de 22,6% acima do teórico.

- **Cálculo do Potenciômetro:** O potenciômetro fará a regulação da voltagem na saída. Sua resistência está relacionada à voltagem mínima de 3V. O valor do ganho de corrente entre o emissor e a base (Veb = 100) e a tensão de drop do transistor (Vdt = 0,7 V) foram retirados do datasheet.

(i) Tensão Máxima de Saída do Potenciômetro:

$$ V_{spmín} = 13 - V_{spmáx} - 0,7 → 3 = 13 - V_{spmáx} - 0,7 → V_{spmáx} = 9,3 V $$

(ii) Corrente no Resistor em Série com o Potenciômetro:

$$ V_{ZENNER} = V_{spmáx} + V_{R2} → 13 = 9,3 + i_{R2} \cdot 2000 → i_{R2} = 1,85 mA $$

(iii) Corrente na Base do Transistor:

$$ i_{BASE} = \frac{i_{coletor-mín}}{G_{base-emissor}} = \frac{3}{120} \times \frac{1}{100} = 0,25 mA $$

Portanto,

$$ R_{pmáx} = \frac{V_{spmáx}}{i_{BASE}+i_{R2}} = \frac{9,3}{(0,25 + 1,85) \cdot 10^{-3}} = 4428,6 Ω $$

No entanto, o valor comercial mais perto do valor teórico é: 5000 Ω

### Circuito FALSTAD
O circuito abaixo representa um esquema simplificado da Fonte de Tensão Regulável. Por meio desse mecanismo, foi possível prever o comportamento de cada um dos componentes eletrônicos no circuito e evitar erros de forma geral.

![Circuito FALSTAD](https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/f93ae96d-fc34-4747-9f10-8326818bc780)

[Link do Circuito](https://tinyurl.com/25z65kpr)

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
| 1 |[Ponte Retificadora](https://www.baudaeletronica.com.br/produto/ponte-retificadora-35a-kbpc3510.html)| KBPC3510 | R$ 12,25 |
| 1     | [Capacitor](https://www.baudaeletronica.com.br/produto/capacitor-eletrolitico-470uf-50v-105c.html)        | 470uF / 50V     | R$ 1,95  |
| 1     | [Potenciômetro](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html)        | Resistência: 5K  | R$ 2,21    |
| 4     | [Resistor 2k2](https://www.casadoresistor.com.br/resistor-filme-carbono-carvao-cr25-1-4w-5-2k2-p272)     | 2200 Ω 1/4W    | R$ 0,06   |
| 1     | [Resistor 120 Ω](https://produto.mercadolivre.com.br/MLB-3037235923-10x-resistor-1w-5-120r-120-ohms-novo-_JM#position=4&search_layout=grid&type=item&tracking_id=ad0f01ce-eae4-4e9f-9a2d-22425ca45e45)     | 120 Ω 1 W    | R$ 1,59   |
| 1     | [Diodo Zener](https://www.baudaeletronica.com.br/diodo-zener-bzx55c-13v-0-5w.html)       | Diodo Zener BZX55C 13V/0,5W     |  R$ 0,08   |
| 1     | [LED Azul](https://www.baudaeletronica.com.br/produto/led-de-alto-brilho-azul)       | 2V/20mA      | R$ 0,27    |
| 1     | [Transistor](https://www.baudaeletronica.com.br/produto/transistor-npn-bc368.html)       |  Transistor NPN - BC368      | R$ 0,55   |

Valor Total: R$ 46,54

OBS.: A ponte retificadora pode ser mais barata (porém optamos em investir uma melhor para ser usada em outros projetos)

### Função dos Componentes

- Transformador: Transforma a tensão alternada da tomada, que possui RMS (root mean square) de 179,6 V, para um valor menor. O seu funcionamento se dá a partir de duas bobinas e a interação entre os seus campos magnéticos, controlando a corrente e a tensão para um valor desejado.

- Diodos: São usados para retificar a corrente alternada. São componentes usados na ponte de diodo que retifica a dupla onda e otimiza a voltagem da tomada através da inversão de um dos semiciclos da função da tensão alternada.

- Capacitor: Armazena a carga durante os picos da corrente alternada, liberando corrente quando a tensão do capacitor é maior que a tensão da fonte.

- Diodo Zener: Conduz corrente elétrica apenas quando a tensão estiver acima da tensão máxima, dessa forma, é possível regular a tensão máxima no circuito.

- Resistores: Limitam a corrente que passam pelos componentes e dissipam calor do circuito.

- Potenciômetro: É um resistor com resistência variável. É utilizado para ajustar a tensão que vai para o transistor.

- Transistor: Utilizado para limitar a passagem de corrente diretamente para a saída. [DATASHEET](https://github.com/FerSuaiden/SSC0180-Eletronica/files/11995178/BC368.PDF)

### Vídeos do projeto funcionando

https://github.com/FerSuaiden/SSC0180-Eletronica/assets/122469265/faed93b2-db19-4c16-be6c-2e7470608e04

### Resposáveis
- Felipe da Costa Coqueiro
- Fernando Alee Suaiden
- Guilherme Torquato
- Adhemar Molon Neto
