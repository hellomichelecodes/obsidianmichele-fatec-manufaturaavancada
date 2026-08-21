Professor: Jorge Sarapka
Sala: Laboratório 15
Semestre: 1º 
tags: #LogicaDeProgramaçãoEmArduino #PrimeiroSemestre #Agosto2026

---

- # Anotações da Aula:
	- **![[Pasted image 20260819164807.png]]

- # Conceitos Importantes
	- #### Conceitos fundamentais apresentados no diagrama da Arquitetura de Von Neumann:
		- **Unidade Central de Processamento (CPU):** O "cérebro" do computador encarregado de executar o programa. Divide-se em:
		    - **Unidade de Controle (UC):** Coordena as operações do sistema, busca a próxima instrução na memória, a decodifica e orienta o fluxo de dados.
		    - **Unidade Lógica e Aritmética (ULA):** Executa os cálculos matemáticos (soma, subtração) e as comparações lógicas (E, OU, NÃO).
		- **Memória Principal Unificada (RAM):** O conceito revolucionário da arquitetura, onde **dados** e **instruções do programa** compartilham o mesmo espaço físico de armazenamento.
		- **Barramentos de Comunicação:** Os canais físicos que conectam a CPU aos componentes internos:
		    - **Barramento de Dados:** Transporta a informação real sendo processada.
		    - **Barramento de Endereço:** Indica a localização exata na RAM onde um dado deve ser lido ou escrito.
		    - **Barramento de Controle:** Transmite sinais de comando (como ordens de leitura ou escrita).
		- **Dispositivos de Entrada e Saída (E/S):** A interface com o mundo exterior. Recebe comandos ou leituras de sensores (Entrada) e envia respostas ou sinais elétricos (Saída).
- # Conteúdos Extras/ Pesquisa:
	- Criação da Máquina Analítica (década de 1830)
		Projetada pelo matemático inglês Charles Babbage, a Máquina Analítica é considerada o primeiro projeto teórico de um computador mecânico de uso geral. Ela já separava o processamento ("Moinho") do armazenamento ("Engrenagens de Memória") e usava cartões perfurados para receber dados e instruções.
	- O Primeiro Código (1843)
		A matemática Ada Lovelace percebeu que a Máquina Analítica de Babbage podia processar mais do que simples números. Ela escreveu o primeiro algoritmo da história — um conjunto de instruções para calcular os números de Bernoulli usando cartões perfurados —, tornando-se a primeira programadora do mundo.
	- O Harvard Mark I e a Arquitetura Harvard (1944)
		Construído por Howard Aiken e a IBM na Universidade de Harvard, este computador eletromecânico usava caminhos físicos separados para dados e instruções: lia o programa em fitas de papel perfuradas e manipulava os dados em contadores eletromecânicos internos. Essa separação deu origem ao termo **Arquitetura Harvard**, o modelo usado pelo microcontrolador do seu Arduino.
	- O Primeiro Computador Eletrônico (1945-1946)
		O ENIAC foi o primeiro computador digital eletrônico de uso geral. No entanto, para mudar de programa, operadoras tinham que reconectar centenas de cabos manualmente. Ele não possuía programa armazenado na memória, exigindo reconfiguração física a cada nova tarefa.
	- A Proposta da Arquitetura de Von Neumann (1945-1949)
		Ao analisar os problemas de reconfiguração manual do ENIAC, o matemático John von Neumann publicou o relatório _"First Draft of a Report on the EDVAC"_. Nele, ele formalizou a **Arquitetura de Von Neumann**: a ideia revolucionária de armazenar tanto o **programa (instruções)** quanto os **dados** na **mesma memória principal (RAM)**, permitindo que o computador mudasse de tarefa apenas carregando um novo software.
		O _Manchester Baby_ (1948) e o _EDSAC_ (1949) foram os primeiros computadores operacionais a implementar na prática o conceito de programa armazenado de Von Neumann. A partir desse momento, a computação moderna nasceu: não era mais necessário mexe em cabos, bastava carregar o código na memória RAM.
	- O Primeiro Desktop Doméstico (1977)
		Com a invenção do microprocessador nos anos 1970 (que integrou a CPU de Von Neumann em um único chip de silício), surgiram os primeiros computadores pessoais comercialmente viáveis em massa, como o **Apple II**, **TRS-80** e o **Commodore PET** em 1977. Eles trouxeram a arquitetura de Von Neumann diretamente para as mesas de casa.
	- O Surgimento do Arduino (2005)
		Criado na Itália para facilitar o ensino de programação e eletrônica, o Arduino utiliza o modelo de **Arquitetura Harvard** para microcontroladores (separando a memória de código Flash da memória de dados SRAM). Essa decisão resgata a estrutura do Harvard Mark I para permitir leitura de instruções e acionamento de portas elétricas simultaneamente em tempo real.
--- 
- # Resumo
	A história da computação evoluiu da separação física de processamento e dados iniciada teoricamente com Charles Babbage e Ada Lovelace na Máquina Analítica e aplicada no eletromecânico Harvard Mark I para a revolução da Arquitetura de Von Neumann formalizada em 1945 e consolidada no Manchester Baby e EDSAC, a qual unificou instruções e dados em uma mesma memória RAM para eliminar as reconfigurações manuais do ENIAC e viabilizar os desktops modernos dos anos 70. Essa estrutura central baseia-se em uma CPU composta por Unidade de Controle e Unidade Lógica e Aritmética acoplada a barramentos de dados, endereço e controle para gerenciar a memória e os dispositivos de entrada e saída. No entanto, o desenvolvimento de microcontroladores modernos como o Arduino resgatou o conceito de Harvard para separar fisicamente as memórias Flash e SRAM, permitindo o processamento de código e o controle de componentes em tempo real com maior eficiência.