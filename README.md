# A03 Paratica Rede Hierarquica
## Objetivo de Resultado:
### O exercício envolve apenas a configuração inicial de um cenário no programa Cisco Packet Tracer considerando os seguintes requisitos:
1) Não é exigida nenhuma configuração de equipamento neste momento, apenas as ligações físicas.
2) Deve-se construir uma rede que tenha de forma visível a estrutura hierárquica, respeitando as características de cada camada (núcleo, distribuição e borda).
3) Deve haver um roteador com duas interfaces fastEthernet, ligando-se a dois switches diferentes.
4) Os dois switches de núcleo devem ter a ligação física para ativação futura de uma agregação de link (link aggregation) de 4Gbps.
5) Os dois switches de núcleo devem ser conectados individualmente a outros dois switches de distribuição por meio de interfaces de fibra óptica. Essas interfaces devem ter a ligação física para ativação futura de uma agregação de link (link aggregation) de 2 Gbps.
6) Devem ser disponibilizados quatro switches de borda, sem qualquer recurso de redundância.
7) Devem ser disponibilizados quatro computadores desktop, quatro notebooks e um servidor (pode ser qualquer um que escolher) todos conectados com fio nessa rede.

## Print do Resultado
![Print Packet Tracer](./Print%20Packet%20Tracer.jpeg)

## Configuração Escolhida

A rede tem três camadas: núcleo, distribuição e acesso. Seguindo a maneira de organização como foi apresentada nas aulas, cada camada tem uma função diferente.

### 1 Camada de núcleo

NUCLEO 1 e NUCLEO 2 são os switches do núcleo. Eles fazem a comutação principal da rede e dão redundância um ao outro.

Os dois estão ligados por 4 cabos de cobre em paralelo. Esses cabos já estão prontos para no futuro virarem um único link de 4 Gbps, mas essa junção ainda não foi ativada — por enquanto são só as ligações físicas.

### 2 Camada de distribuição

DIST 1 junta os switches ACESSO 1 e ACESSO 2. DIST 2 junta os switches ACESSO 3 e ACESSO 4.

Cada switch de distribuição se liga aos dois switches de núcleo, usando fibra óptica. Cada ligação usa 2 fibras em paralelo, prontas para virar um link de 2 Gbps (ainda não ativado). No total são 4 ligações e 8 fibras.

Essa ligação cruzada (cada distribuição ligada aos dois núcleos) garante que, se um switch de núcleo falhar, a rede continua funcionando pelo outro.

### 3 Camada de acesso

Os switches de acesso são: ACESSO 1 (PC0, PC1), ACESSO 2 (PC2, PC3), ACESSO 3 (Laptop0, Laptop1) e ACESSO 4 (Laptop2, Laptop3, Server0).

Cada switch de acesso sobe para a distribuição com apenas um cabo. Não tem redundância nessa camada.

### 4 Roteador

O Router0 tem duas portas ligadas ao núcleo:

FastEthernet0/0 → NUCLEO 1
FastEthernet0/1 → NUCLEO 2

### 5 Dispositivos finais

9 dispositivos no total, todos com fio: 4 PCs (PC0 a PC3), 4 notebooks (Laptop0 a Laptop3) e 1 servidor (Server0).

## EXTRA: Configuração dos Endereços IP
O teste dos pings foram realizados e concluídos com sucesso!
![Teste dos Pings I](./Teste%20dos%20Pings%20I.jpeg)

![Teste de Pings II](./Teste%20de%20Pings%20II.jpeg)
