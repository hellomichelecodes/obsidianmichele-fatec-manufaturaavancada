# PROJETO: Limpeza Industrial Automatizada (LIA)

- # 1. Definição da Proposta
	- ## 1.1 Operação de execução
		- Varrição, lavagem, desinfecção por radiação UV-C e secagem autônoma noturna de pavimentos de epóxi e poliuretano em áreas de embalagem, salas limpas (classes ISO 5 a 8) e linhas de processamento fabril. A operação elimina contaminações químicas e microbiológicas sem interferir na produção do turno diurno.
	- ## 1.2 Principais requisitos operacionais
		- Operação contínua de até 6 horas por carga, navegação autônoma em corredores estreitos com desvio dinâmico de obstáculos, mapeamento em tempo real, doca para autocarregamento e troca de fluidos, além de taxa de eliminação microbiana de 99,9% auditável via sistema.
	- ## 1.3 Ambiente de operação
		- Pisos industriais de alta resistência em áreas de processamento, montagem e salas limpas das indústrias farmacêutica, biotecnológica e de alimentos.
	- ## 1.4 Tecnologias da Indústria 4.0 integradas ao projeto
		- Robótica Móvel Autônoma (AMR), Navegação por Mapeamento e Localização Simultâneos (SLAM LiDAR 2D/3D), Internet das Coisas (IoT) para telemetria de insumos e tempo de ciclo, Computação na Nuvem e integração com os sistemas de gestão da fábrica (MES/ERP). 
- # 2. Resumo da Proposta
	A manutenção dos padrões rigorosos de higienização de pisos nas indústrias farmacêuticas e alimentícias depende historicamente de mão de obra manual noturna. Esse processo gera altos custos operacionais, variação na qualidade da desinfecção e riscos de contaminação cruzada por falha humana. Para resolver essa vulnerabilidade no suporte à linha de produção, propõe-se o desenvolvimento de um Robô Móvel Autônomo (AMR) especializado na sanitização e higienização de pavimentos industriais.
	O sistema utiliza um chassi com tração diferencial acoplado a um módulo robótico de escovação, sucção de fluidos e lâmpadas germicidas UV-C para eliminação de patógenos. Aplicada nas áreas limpas e nos corredores de produção, a solução opera durante o período ocioso da planta sem necessidade de supervisão humana direta. Como principais benefícios, o projeto entrega padronização do processo com emissão de relatórios auditáveis via IoT, redução de até 40% no consumo de água e insumos químicos por meio de dosagem inteligente, eliminação da exposição humana a produtos tóxicos e redução expressiva de custos com jornadas noturnas insalubres.
- # 3. Pesquisa de Aplicações Semelhantes
	- ## 3.1 **Onde foi encontrada:** 
		Base de dados IEEE Xplore e especificações técnicas de robôs industriais de higienização de pisos ( MiR - Mobile Industrial Robots e Nilfisk Liberty SC50).
	- ## 3.2 **O que foi desenvolvido:** 
		Robô autônomo industrial voltado para varrição, lavagem e aspiração contínua de grandes superfícies de piso em ambientes logísticos e fabris.
	- ## 3.3 Qual problema foi resolvido:
		A ineficiência, o elevado custo com horas extras e a ausência de rastreabilidade na limpeza manual de grandes áreas industriais sensíveis.
	- ## 3.4 Qual tecnologia foi utilizada:
		Módulos LiDAR 2D/3D para mapeamento do ambiente, odometria por encoders em rodas, sensores ultrassônicos anti-colisão, algoritmo de navegação SLAM baseado em ROS (_Robot Operating System_) e módulos Wi-Fi/4G para comunicação IoT.
	- ## 3.5 O que pode ser aproveitado como referência para o projeto do grupo:
		A arquitetura do sistema SLAM para navegação e desvio dinâmico de empilhadeiras e operadores, além do mecanismo de doca autônoma para recarga da bateria e abastecimento/descarte de fluidos de limpeza.
- # 4. Conclusão
	- Em suma, o projeto Limpeza Industrial Automatizada (LIA) consolida-se como uma solução inovadora e estrategicamente alinhada aos preceitos da Indústria 4.0, respondendo de forma direta aos gargalos de custo, insalubridade e variabilidade do processo de higienização manual. Ao combinar navegação autônoma avançada (SLAM LiDAR), conectividade IoT para auditabilidade total e um ciclo multifuncional de sanitização (incluindo radiação UV-C), o AMR garante máxima eficiência microbiológica nas áreas mais críticas da planta. Dessa forma, a proposta não apenas otimiza o uso de recursos e reduz custos operacionais, mas também estabelece um novo padrão de segurança, padronização e rastreabilidade para o setor fabril.