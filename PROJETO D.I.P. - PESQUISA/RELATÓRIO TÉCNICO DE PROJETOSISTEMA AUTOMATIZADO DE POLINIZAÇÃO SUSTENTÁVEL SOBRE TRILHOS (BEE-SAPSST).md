### **SUMÁRIO**

1. **INTRODUÇÃO E ESCOPO**
    - 1.1 Apresentação do Problema
    - 1.2 Escopo do Projeto
    - 1.3 Objetivos
2. **ARQUITETURA DE HARDWARE E COMPONENTES**
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

#### **1.1 Apresentação do Problema**

A polinização animal incrementa a produtividade de mais de $75\%$ das principais culturas de alimentos do mundo. O transporte migratório tradicional de colmeias, porém, é majoritariamente feito por caminhões o que expõe as colônias a severos níveis de vibração, poluição e oscilações térmicas, fatores fortemente associados ao estresse do enxame e ao Colapso das Colônias.
#### **1.2 Escopo**

Este trabalho apresenta a modelagem teórica e o dimensionamento eletromecânico do **BEE-SAPST**, um sistema robótico automatizado controlado pela plataforma Arduino para transporte e manejo de colmeias em estufas e lavouras.

- **Abrangência:**
    - Cinemática de movimento suave sobre trilhos via rampa de aceleração trapezoidal.
    - Telemetria microclimática (temperatura, umidade e peso) e detecção de janelas de voo.
    - Algoritmo de controle seguro baseado em Máquina de Estados Finitos (FSM) e interrupções climáticas.
- **Limitações:** Prototipagem física em escala real e testes biológicos _in situ_ estão fora do escopo do presente semestre.
#### **1.3 Objetivos**

- **Geral:** Projetar teoricamente um sistema robótico automatizado sobre trilhos para suporte, movimentação e monitoramento de colmeias, assegurando o bem-estar dos polinizadores.
- **Específicos:**
    1. Dimensionar a mecânica de tração e o motor de passo.
    2. Desenvolver a arquitetura de sensores ambientais.
    3. Modelar a lógica do firmware (FSM) com travas de segurança e rotinas de _homing_.