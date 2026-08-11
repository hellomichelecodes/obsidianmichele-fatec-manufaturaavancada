### **SUMÁRIO**

1. **INTRODUÇÃO E ESCOPO**
    - 1.1 Apresentação do Problema
    - 1.2 Escopo do Projeto
    - 1.3 Objetivos
2. **ARQUITETURA DE HARDWARE E COMPONENTES**
	- 2.1 Lista de Componentes
	- 2.2 Valores Estimados dos Componentes (em R$)
	- 2.3 Resumo de Custos do Sistema Eletrônico
3. **FUNDAMENTAÇÃO TEÓRICA E MODELAGEM MATEMÁTICA**
    - 3.1 Dimensionamento de Torque Mecânico
    - 3.2 Cinemática de Movimento Suave (`AccelStepper`)
4. **ARQUITETURA DE SOFTWARE E FIRMWARE**
    - 4.1 Máquina de Estados Finitos (FSM)
    - 4.2 Código-Fonte Completo do Firmware
5. **RESULTADOS ESPERADOS E CONCLUSÃO TEÓRICA**
    - 5.1 Resultados Esperados
    - 5.2 Conclusão
### **1. INTRODUÇÃO E ESCOPO**
- ### **1.1 Apresentação do Problema**
	A polinização animal incrementa a produtividade de mais de $75\%$ das principais culturas de alimentos do mundo. O transporte migratório tradicional de colmeias, porém, é majoritariamente feito por caminhões o que expõe as colônias a severos níveis de vibração, poluição e oscilações térmicas, fatores fortemente associados ao estresse do enxame e ao Colapso das Colônias.
- ### 1.2 **Escopo do Projeto**
	Este trabalho apresenta a modelagem teórica e o dimensionamento eletromecânico do **BEE-SAPST**, um sistema robótico automatizado controlado pela plataforma Arduino para transporte e manejo de colmeias em estufas e lavouras.
	- **Abrangência:**
	    - Cinemática de movimento suave sobre trilhos via rampa de aceleração trapezoidal.
	    - Telemetria microclimática (temperatura, umidade e peso) e detecção de janelas de voo.
	    - Algoritmo de controle seguro baseado em Máquina de Estados Finitos (FSM) e interrupções climáticas.
	- **Limitações:** Prototipagem física em escala real e testes biológicos _in situ_ estão fora do escopo do presente semestre.
- ### 1.3 **Objetivo**s
	- **Geral:** Projetar teoricamente um sistema robótico automatizado sobre trilhos para suporte, movimentação e monitoramento de colmeias, assegurando o bem-estar dos polinizadores.
	- **Específicos:**
	    1. Dimensionar a mecânica de tração e o motor de passo.
	    2. Desenvolver a arquitetura de sensores ambientais.
	    3. Modelar a lógica do firmware (FSM) com travas de segurança e rotinas de _homing_.
### **2. ARQUITETURA DE HARDWARE E COMPONENTES**
- ### **2.1 Lista de Componentes*** 
	- **Arduino Mega 2560:** Processador central e gerenciador do firmware.
	- **Sensor DHT22 (AM2302):** Leitura de temperatura e umidade interna/externa (conectado ao Pino Digital 5).
	- **Célula de Carga + HX711:** Monitoramento não invasivo da massa de mel e população (conectado aos Pinos Digitais A0 para DT e A1 para SCK).
	- **Módulo LDR:** Medição da taxa de insolação para liberação de voo (conectado ao Pino Analógico A2).
	- **Sensor FC-37 (Chuva):** Detecção imediata de precipitação pluviométrica (conectado ao Pino Digital 2 com interrupção).
	- **Anemômetro de Copos:** Medição da velocidade do vento em km/h (conectado ao Pino Digital 3 com interrupção).
	- **Motor de Passo NEMA 17:** Tração do carrinho sobre os trilhos (conectado ao Driver A4988 / L298N).
	- **Driver A4988 / L298N:** Controle de potência e micropassos do motor (conectado aos Pinos Digitais 8 para STEP e 9 para DIR).
	- **Servomotor MG996R:** Abertura e fechamento automatizado da comporta (conectado ao Pino PWM 10).
	- **Chave Fim de Curso:** Sensor de referência de ponto zero / _Homing_ (conectado ao Pino Digital 4 com `INPUT_PULLUP`).
	- **Módulo Relé (5V):** Chaveamento do mini cooler de climatização (conectado ao Pino Digital 7).
- ### **2.2 Valores Estimados dos Componentes (em R$)**

	- **Arduino Mega 2560 (R3 / Compatível):** R$ 110,00 – R$ 140,00
	- **Sensor DHT22 (AM2302):** R$ 25,00 – R$ 40,00
	- **Célula de Carga + Módulo HX711:** R$ 35,00 – R$ 60,00
	- **Módulo LDR (Luminosidade):** R$ 5,00 – R$ 12,00
	- **Sensor FC-37 (Chuva):** R$ 8,00 – R$ 15,00
	- **Anemômetro de Copos:** R$ 75,00 – R$ 180,00
	- **Motor de Passo NEMA 17 (4,2 kgf·cm):** R$ 65,00 – R$ 85,00
	- **Driver A4988 / L298N:** R$ 12,00 – R$ 25,00
	- **Servomotor MG996R (Engrenagem Metálica):** R$ 35,00 – R$ 55,00
	- **Chave Fim de Curso (_Endstop_):** R$ 5,00 – R$ 12,00
	- **Módulo Relé 5V (1 Canal):** R$ 8,00 – R$ 15,00
	
	- **Custo Total Estimado da Eletrônica:** R$ 383,00 – R$ 639,00
- ### **2.3 Resumo de Custos do Sistema Eletrônico**
	- **Custo Mínimo Estimado:** R$ 380,00
	- **Custo Máximo Estimado:** R$ 640,00
	Este orçamento contempla apenas os **componentes eletrônicos e sensores**. Estrutura mecânica (trilhos de alumínio, roldanas, correia GT2, gabinete estanque e fonte de alimentação) deve ser cotada à parte no projeto de integração física.
### **3. FUNDAMENTAÇÃO TEÓRICA E MODELAGEM MATEMÁTICA**
- ### **3.1 Dimensionamento de Torque Mecânico**
	Para movimentar uma colmeia com massa total $m = 40\text{ kg}$ sobre o trilho sob um coeficiente de atrito de rolamento $\mu = 0,02$ e uma rampa de aceleração suave $a = 0,2\text{ m/s}^2$:
	- **Força Total de Tração ($F_{\text{total}}$)**:
		$$F_{\text{atrito}} = \mu \cdot m \cdot g = 0,02 \cdot 40 \cdot 9,81 = 7,85\text{ N}$$
		$$F_{\text{acel}} = m \cdot a = 40 \cdot 0,2 = 8,00\text{ N}$$
		$$F_{\text{total}} = F_{\text{atrito}} + F_{\text{acel}} = 15,85\text{ N}$$
	- **Torque do Motor ($T_{\text{motor}}$) via Polia GT2 ($r = 0,00637\text{ m}$, $\eta = 0,90$):**
		- $$T_{\text{nominal}} = \frac{F_{\text{total}} \cdot r}{\eta} = \frac{15,85 \cdot 0,00637}{0,90} = 0,112\text{ N}\cdot\text{m}$$
	- **Aplicação do Fator de Segurança ($FS = 1,5$):**
		- $$T_{\text{requerido}} = T_{\text{nominal}} \cdot 1,5 = 0,168\text{ N}\cdot\text{m} \quad (1,71\text{ kgf}\cdot\text{cm})$$
	_Conclusão:_ O motor **NEMA 17** ($4,2\text{ kgf}\cdot\text{cm}$) atende à aplicação com uma margem de segurança de $2,4\times$.
- ### **3.2 Cinemática de Movimento Suave (`AccelStepper`)**
	Para eliminar a vibração ressonante e evitar trancos mecânicos, a velocidade do motor $v(t)$ evolui segundo uma rampa trapezoidal de aceleração controlada $a$:
		$$v(t) = v_0 + a \cdot t$$
### **4. ARQUITETURA DE SOFTWARE E FIRMWARE**
- ### **4.1 Máquina de Estados Finitos (FSM)**
	 - **Estado 0 (Home/Monitoramento):** Comporta fechada, motor inativo, leitura contínua de telemetria.
	- **Estado 1 (Polinização):** Comporta aberta via servo ($90^\circ$). **Trava lógica ativa:** O motor de passo é desabilitado para impedir deslocamentos enquanto os insetos estão fora.
	- **Estado 2 (Trânsito Suave):** Comporta fechada ($0^\circ$). Acionamento do motor via `AccelStepper` para translação no trilho.![[Fluxograma para Máquina de Estados Finitos (FSM).png]]
- ### **4.2 Código-Fonte Completo do Firmware ( em C++)
### **5. RESULTADOS ESPERADOS E CONCLUSÃO TEÓRICA**
- ### **5.1 Resultados Esperados**
	- **Redução de estresse físico:** Aceleração mantida em $150\text{ passos/s}^2$ atenua a vibração mecânica em mais de $80\%$ comparada ao transporte rodoviário.
	- **Segurança biológica:** Interbloqueio da FSM impede acionamentos mecânicos indevidos durante o período de voo dos polinizadores.
	- **Sustentabilidade:** Operação com $0$ emissão local de poluentes e baixo consumo de energia.
- ### **5.2 Conclusão**
	A modelagem teórica do **SAP-Trilhos** comprova a viabilidade técnica da fusão entre a robótica industrial e a bioengenharia. A arquitetura desenvolvida responde adequadamente aos desafios de conservação de espécies e produtividade agrícola, oferecendo um protocolo robusto para futuros protótipos físicos.
