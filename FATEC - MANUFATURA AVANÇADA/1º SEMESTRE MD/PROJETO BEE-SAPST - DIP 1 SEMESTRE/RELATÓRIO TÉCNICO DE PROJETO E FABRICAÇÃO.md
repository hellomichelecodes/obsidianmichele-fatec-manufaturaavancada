**AUTORES:** Ivan, Michele, Pedro, Thayna
**INSTITUIÇÃO:** Faculdade de Tecnologia de São Bernardo do Campo “Adib Moisés Dib”
**DISCIPLINA:** Desenvolvimento Integrado do Produto ( D.I.P.)
**PROFESSOR:** Rafael Russi
**PROJETO:** Sistema Automatizado de Polinização Sobre Trilhos ( BEE-SAPST)
### **PRÓLOGO**
A polinização animal é um dos pilares mais críticos da segurança alimentar global, sendo responsável direta pelo incremento da produtividade de mais de 75% das principais culturas agrícolas do planeta. No entanto, o equilíbrio desse serviço ecossistêmico enfrenta uma ameaça sem precedentes. O declínio acelerado das populações de polinizadores — fenômeno associado ao Colapso das Colônias (CCD) — coloca em risco a biodiversidade, a estabilidade dos ecossistemas e a eficiência do agronegócio moderno.
Para suprir a demanda por polinização em grandes lavouras e estufas, a agricultura comercial recorreu historicamente ao transporte migratório de colmeias. Contudo, o método tradicional baseado no uso de caminhões tornou-se um dos principais vetores do estresse apícola. As longas jornadas sobre estradas irregulares submetem os enxames a:
	- **Vibrações mecânicas intensas e choques contínuos**, que rompem a estrutura interna dos favos de mel e causam mortalidade física direta de operárias e da rainha;
	- **Oscilações térmicas e sufocamento**, decorrentes do confinamento prolongado e do fluxo de ar inadequado nas caixas empilhadas;
	- **Exposição a poluentes e fumaça de combustão**, afetando a orientação neurobiológica dos insetos.
Diante desse cenário, surge a necessidade urgente de soluções tecnológicas que conciliem a eficiência do manejo agrícola com o bem-estar biológico dos enxames.
O projeto **BEE-SAPST (Sistema Automatizado de Polinização Sustentável sobre Trilhos)** foi concebido como uma resposta direta a esse desafio. Trata-se de uma plataforma robótica sobre trilhos projetada para automatizar o transporte e a telemetria de colmeias em lavouras e estufas agrícolas. O sistema fundamenta-se nos seguintes pilares centrais:
	- **Arquitetura Híbrida e Biocompatível:** Combinação do uso da madeira natural para os módulos da colmeia (garantindo isolamento térmico e acústico ideal ao enxame) com carcaças em polímeros de alta resistência (ASA/PETG) para a proteção dos sistemas eletrônicos; 
	- **Cinemática de Aceleração Suave:** Emprego de movimentação sobre guias lineares com aceleração controlada (rampa trapezoidal), atenuando em mais de 80% as vibrações mecânicas em comparação ao transporte rodoviário
	- **Monitoramento e Automação Inteligente:** Leitura contínua de parâmetros microclimáticos (temperatura, umidade, peso e luminosidade) integrada a travas lógicas de segurança que protegem as abelhas durante suas janelas de voo e diante de intempéries;
	- **Escalabilidade e Autonomia:** Chassi projetado para suportar até 80 kg de carga operacional com motores de passo industriais, contando com sistema autônomo de recarga elétrica por contato no ponto de descanso.
O BEE-SAPST une a robótica, a manufatura aditiva e a bioengenharia para transformar o manejo apícola tradicional em uma operação sustentável, previsível e ecologicamente segura.
### **SUMÁRIO**

1. **INTRODUÇÃO E ESCOPO**
    - 1.1 Apresentação do Problema
    - 1.2 Escopo do Projeto
    - 1.3 Objetivos
2. **ARQUITETURA DE HARDWARE E CUSTOS**
	- 2.1 Lista de Componentes Eletrônicos
	- 2.2 Componentes Mecânicos e Estruturais Industriais
	- 2.3 Resumo do Orçamento Integrado
3. **MODELAGEM MATEMÁTICA E DIMENSIONAMENTO MECÂNICO**
    - 3.1 Dimensionamento de Torque (Carga Real de 80 kg)
    - 3.2 Estratégia de Teste Acadêmico (NEMA 17 vs. NEMA 23)
      - 3.3 Cinemática de Movimento Suave (AccelStepper)
4. **PROJETO MECÂNICO, MATERIAIS E IMPRESSÃO 3D** 
	- 4.1 Diretrizes de Bio-segurança e Materiais
	- 4.2 Guias Lineares e Roldanas Industriais
	- 4.3 Especificações de Manufatura Aditiva (Parâmetros de Impressão)
	- 4.4 Tolerâncias Mecânicas e Montagem Híbrida
	- 4.5 Sistema de Amortecimento e Recarga por Contato
5. **ARQUITETURA DE SOFTWARE E FIRMWARE**
    - 5.1 Lógica da Máquina de Estados Finitos (FSM)
    - 5.2 Proteção Climática e Interrupções
6. **RESULTADOS ESPERADOS E CONCLUSÃO TEÓRICA**
### **1. INTRODUÇÃO E ESCOPO**

- ### **1.1 Apresentação do Problema**
	A polinização animal incrementa a produtividade de mais de 75% das principais culturas de alimentos do mundo. O transporte migratório tradicional de colmeias por caminhões expõe as colônias a severos níveis de vibração, poluição e oscilações térmicas, fatores fortemente associados ao estresse do enxame e ao Colapso das Colônias (CCD).
	
- ### 1.2 **Escopo do Projeto e Conceito Híbrido**
	Este trabalho apresenta o projeto completo e dimensionamento do BEE-SAPST, um robô automatizado sobre trilhos para transporte de colmeias em estufas e lavouras. O projeto adota uma **arquitetura híbrida**:
	- **Estrutura Biológica (Colmeia):** Feita em madeira natural tratada (ex.: Pinus ou Cedro), mantendo a tradição do manejo apícola e proporcionando isolamento térmico e acústico ideal.
	- **Chassi e Cúpula (Automação):** Manufaturados via impressão 3D (ASA/PETG) para alocar os componentes eletrônicos, sensores e acoplamentos.
	- **Trilho e Tração:** Guias metálicas e perfis de alumínio industriais comprados à parte para suportar altas cargas.
	
- ### 1.3 **Objetivo**s
	- **Geral:** Projetar e validar teoricamente um sistema robótico automatizado sobre trilhos para suporte, movimentação e monitoramento microclimático de colmeias.
	- **Específicos:** Dimensionar a tração mecânica para a carga real de $80\text{ kg}$; projetar o chassi impresso em 3D compatível com NEMA 17 e NEMA 23; implementar o firmware baseado em Máquina de Estados Finitos (FSM).
### **2. ARQUITETURA DE HARDWARE E CUSTOS
- ### **2.1 Lista de Componentes Eletrônicos*** 
	- **Microcontrolador Central:** Arduino Mega 2560 R3.
	- **Telemetria Microclimática:** Sensor DHT22 (Pino D5) para temperatura e umidade.
	- **Monitoramento de Peso:** Célula de Carga com módulo HX711 (Pinos A0/A1).
	- **Luminosidade:** Módulo LDR para taxa de insolação (Pino A2).
	- **Segurança Climática:** Sensor FC-37 para chuva (Pino D2) e Anemômetro de copos para vento (Pino D3).
	- **Atuadores de Tração e Porta:** Driver A4988 / L298N (Pinos D8/D9); Servomotor MG996R para comporta (Pino PWM D10); Motor de passo (NEMA 17 em bancada / NEMA 23 em campo).
	- **Auxiliares e Fim de Curso:** Endstop Mecânico (Pino D4); Módulo Relé 5V para mini-cooler (Pino D7).
- ### **2.2 Componentes Mecânicos e Estruturais Industriais
	- Perfil de alumínio estrutural $40\times 40\text{ mm}$ e guia linear metálica (ex.: SBR20 ou MGN15).
	- Correia síncrona GT2 reforçada ($9\text{ mm}$ a $15\text{ mm}$) e polia de alumínio de 20 dentes.
	- Placa base de madeira de reflorestamento para as gavetas hexagonais.
- ### **2.3 Resumo do Orçamento Integrado**
	- **Eletrônica e Sensores:** R$ 380,00 – R$ 640,00
	- **Trilhos e Guias Lineares:** R$ 180,00 – R$ 350,00
	- **Filamentos 3D (ASA/PETG/TPU):** R$ 120,00 – R$ 200,00
	- **Madeira e Hardware (Inox):** R$ 90,00 – R$ 160,00
	- **Custo Total Estimado:** R$ 770,00 – R$ 1.350,00
### **3. MODELAGEM MATEMÁTICA E DIMENSIONAMENTO MECÂNICO**

- ### **3.1 Dimensionamento de Torque (Carga Real de 80 kg)
	Considerando a carga real de uma colmeia cheia com $m = 80\text{ kg}$, coeficiente de atrito de rolamento em guias lineares $\mu = 0{,}02$, e aceleração suave $a = 0{,}2\text{ m/s}^2$:
	- **3.1.1. Força Total de Tração ($F_{\text{total}}$)**:
	$$F_{\text{atrito}} = \mu \cdot m \cdot g = 0{,}02 \cdot 80 \cdot 9{,}81 = 15{,}70\text{ N}$$
		$$F_{\text{acel}} = m \cdot a = 80 \cdot 0{,}2 = 16{,}00\text{ N}$$
		$$F_{\text{total}} = F_{\text{atrito}} + F_{\text{acel}} = 31{,}70\text{ N}$$
	- **3.1.2. Torque Nominal ($T_{\text{nominal}}$) com Polia GT2 ($r = 0{,}00637\text{ m}$, $\eta = 0{,}90$):**
		$$T_{\text{nominal}} = \frac{F_{\text{total}} \cdot r}{\eta} = \frac{31{,}70 \cdot 0{,}00637}{0{,}90} = 0{,}224\text{ N}\cdot\text{m}$$
	- **3.1.3. Torque Requerido com Fator de Segurança ($FS = 1{,}5$):**
		$$T_{\text{requerido}} = T_{\text{nominal}} \cdot 1{,}5 = 0{,}336\text{ N}\cdot\text{m} \quad (3{,}42\text{ kgf}\cdot\text{cm})$$
- ### **3.2. Estratégia de Teste Acadêmico (NEMA 17 vs. NEMA 23)
	- **Aplicação Final (Campo):** O motor **NEMA 23** (torques de $12$ a $30\text{ kgf}\cdot\text{cm}$) é o especificado para mover a carga real de $80\text{ kg}$ com ampla margem contra travamentos.
	- **Protótipo Acadêmico (Bancada):** Utiliza-se um motor **NEMA 17** ($4{,}2\text{ kgf}\cdot\text{cm}$), plenamente capaz de validar a cinemática e o firmware sem carga total. A carcaça possui furação universal para ambos.
- ### **3.3. Cinemática de Movimento Suave
	Para impedir trancos que estressem as abelhas, a velocidade evolui em rampa trapezoidal controlada via biblioteca `AccelStepper`, limitando a aceleração a $150\text{ passos/s}^2$.
### 4. PROJETO MECÂNICO, MATERIAIS E IMPRESSÃO 3D
- ### 4.1 Diretrizes de Bio-segurança e Materiais
	- **Colmeia (Madeira Natural):** Proteção térmica/acústica inerte, livre de tintas tóxicas.
	- **Cúpula da Eletrônica (ASA Amarelo):** Alta resistência a raios UV e calor de estufas.
	- **Base do Trilho (ASA/PETG Preto):** Resposta estrutural e imunidade à umidade do solo.
	- **Amortecedores (TPU Flexível):** Absorção de microvibrações mecânicas.
	- **Fixação:** Parafusos e porcas exclusivamente em **Aço Inoxidável 304**.
- ### **4.2 Guias Lineares e Roldanas Industriais
	Para impedir o desgaste das peças impressas, a carga vertical de $80\text{ kg}$ é descarregada diretamente nos patins de aço das guias lineares industriais. Os componentes 3D funcionam como o "chassi de arraste" e invólucro de proteção.
- ### **4.3 Especificações de Manufatura Aditiva
	- **Material da Cúpula e Base:** ASA ou PETG (resistentes a UV e umidade)
	- **Material dos Coxins e Gaxetas:** TPU (Shore 95A / 85A)
	- **Altura de Camada:** 0,20 mm
	- **Perímetros (Paredes):** 5 camadas
	- **Camadas de Topo e Base:** 5 camadas
	- **Preenchimento (Infill):** 40% (Padrão Gyroid para resistência isotrópica)
#### 4.3 Especificações de Manufatura Aditiva

### **5. ARQUITETURA DE SOFTWARE E FIRMWARE**

- ### **5.1 Lógica da Máquina de Estados Finitos (FSM)**
	- **Estado 0 (Home/Monitoramento):** Comporta fechada, motor inativo, leitura contínua de sensores microclimáticos e carregamento na base.
	- **Estado 1 (Polinização):** Comporta aberta via servomotor ($90^\circ$). **Trava de Segurança:** O motor de passo é desabilitado fisicamente via software para impedir acionamentos com abelhas fora da caixa.
	- **Estado 2 (Trânsito Suave):** Comporta fechada ($0^\circ$). Tração via `AccelStepper` até a próxima coordenada.
- ### **5.2 Proteção Climática e Interrupções**
	Se o sensor FC-37 detectar chuva ou o anemômetro registrar vento superior ao limite seguro ($>20\text{ km/h}$), o sistema força a transição para o **Estado 0**, fecha a comporta e recolhe o carrinho para a base coberta.
### **6. RESULTADOS ESPERADOS E CONCLUSÃO**
- ### **6.1 Resultados Esperados**
	- **Preservação Biológica:** Aceleração mantida em $150\text{ passos/s}^2$ atenua a vibração em mais de $80\%$ em relação ao transporte de carga sobre rodas pneumáticas.
	- **Integridade Térmica:** A combinação do corpo de madeira natural com o monitoramento por sensores garante a estabilidade climática do enxame.
	- **Confiabilidade Mecânica:** A carcaça adaptável suporta o protótipo de bancada em NEMA 17 e garante escalabilidade total para o motor NEMA 23 operando a $80\text{ kg}$.
- ### **6.2 Conclusão**
	O projeto **BEE-SAPST** demonstra a viabilidade de unir a robótica industrial, a manufatura aditiva e o manejo apícola tradicional. A arquitetura técnica apresentada soluciona as limitações de carga, viabiliza o protótipo acadêmico com baixo custo e entrega um modelo seguro para aplicação em campo.