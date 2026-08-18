# **PROJETO:** Sistema Automatizado de Polinização Sobre Trilhos ( BEE-SAPST)

- # **1. Definição da Proposta**
	- ## **Qual é a tarefa/operação que o robô executará na manufatura avançada?** 
		- O robô executará o transporte automatizado, a movimentação suave e a telemetria microclimática contínua de colmeias de abelhas ao longo de lavouras e estufas agrícolas. Além do transporte, ele realiza a abertura/fechamento automatizado de comportas de acesso (janela de voo) e gerencia o recolhimento automático da colônia.
	
	- ## **Quais são os principais requisitos operacionais?**
		- **Capacidade de Carga e Tração:** Suportar até 80 kg de carga útil (peso de colmeias cheias).
		- **Cinemática Suave:** Movimentação com rampa de aceleração suave/trapezoidal (limitada a 150 passos/s²), reduzindo em mais de 80% as vibrações mecânicas para evitar estresse apícola e destruição dos favos.
		- **Segurança Biológica e Climática:** Travamento lógico do motor durante janelas de polinização e recolhimento autônomo ao ponto de descanso coberto sob condições adversas (chuva ou vento acima de 20 km/h).
		- **Autonomia Elétrica:** Sistema de recarga automática por contato no ponto de descanso.
	
	- ## **Qual é o ambiente de operação?** 
		- Ambientes agrícolas fechados ou abertos, tais como estufas comerciais e lavouras. O sistema opera em trilhos e guias lineares com alta exposição a intempéries, raios UV, umidade e poeira.
	
	- ## **Quais tecnologias da Indústria 4.0 serão integrated ao projeto?**
		- **Robótica Móvel/Automação de Guias Lineares:** AGV sobre trilhos acionado por motores de passo industriais com aceleração controlada (biblioteca AccelStepper).
		- **Internet das Coisas (IoT) e Telemetria Microclimática:** Monitoramento contínuo de temperatura, umidade, peso e luminosidade (DHT22, HX711, LDR) integrados a um microcontrolador (Arduino Mega 2560).
		- **Manufatura Aditiva (Impressão 3D):** Produção do chassi de arraste e cúpula protetora em polímeros industriais (ASA, PETG e TPU) com resistência térmica e flexibilidade de amortecimento.
		- **Sistemas Embarcados e Arquitetura FSM:** Controle via Máquina de Estados Finitos com acionamento de atuadores e travas lógicas baseadas em sensores de interrupção.

- # **2. Resumo da Proposta**
	O agronegócio moderno depende fortemente da polinização para manter a produtividade de mais de 75% das culturas. Contudo, o transporte migratório tradicional de colmeias realizado por caminhões expõe as abelhas a vibrações severas, choques mecânicos, estresse térmico e poluição, sendo um dos fatores associados ao Colapso das Colônias (CCD). Para solucionar esse gargalo ecológico e operacional, propõe-se o projeto BEE-SAPST (Sistema Automatizado de Polinização Sustentável sobre Trilhos). Trata-se de um sistema robótico móvel tipo AGV sobre trilhos projetado para automatizar o deslocamento, a segurança e a telemetria das colmeias. A solução será aplicada diretamente em estufas e lavouras agrícolas comerciais. O sistema adota uma arquitetura híbrida, combinando madeira natural para alojamento térmico e acústico do enxame com carcaças impressas em 3D (ASA/PETG/TPU) e guias lineares metálicas. Os principais benefícios esperados incluem a atenuação de mais de 80% das vibrações mecânicas, o controle de janelas de voo com recolhimento automático diante de tempestades, a mitigação do estresse apícola e a garantia de maior previsibilidade na polinização agrícola.

- # **3. Pesquisa de Aplicações Semelhantes**
	- ## **Onde foi encontrada?** 
		- Sistemas de logística interna agrotecnológica / Projetos Acadêmicos de Agrotech em Automação e Mecatrônica.
	- ## **O que foi desenvolvido?** 
		- Sistemas robóticos e veículos guiados autonomamente (AGVs) para manejo agrícola em estufas, voltados ao transporte de colmeias migratórias e monitoramento de microclima através de sensores ambientais e acionamento mecânico suave.
	- ## **Qual problema foi resolvido?** 
		- O estresse mecânico e a mortalidade das abelhas decorrentes do transporte rodoviário em estradas irregulares, que causam a ruptura de favos de mel, perda de operárias e abandono da colmeia.
	- ## **Qual tecnologia foi utilizada?**
		- Sensores de telemetria microclimática (temperatura, umidade, peso e luz).
		- Sistemas de tração mecânica com fuso ou correia síncrona acionados por motores de passo.
		- Impressão 3D de invólucros protetores com termoplásticos resistentes ao tempo e amortecedores em elastômeros.
		- Lógica de controle embarcada com rotinas em FSM para automação segura.

- # **4. O que pode ser aproveitado como referência para o projeto do grupo?**
	- **Controle Cinematográfico Suave:** A adoção de controle por rampa trapezoidal de aceleração para eliminar solavancos de partida e parada, protegendo a estrutura física da colmeia.
	- **Modularidade Estrutural Híbrida:** A integração do uso da madeira (biocompatibilidade térmica) acoplada a um chassi técnico em impressão 3D (ASA/PETG) para contenção eletrônica.
	- **Lógica de Segurança Ante Intempéries:** A implementação de uma máquina de estados finitos que prioriza a interrupção de operações e o recolhimento do veículo sob sinais de chuva ou ventos fortes.