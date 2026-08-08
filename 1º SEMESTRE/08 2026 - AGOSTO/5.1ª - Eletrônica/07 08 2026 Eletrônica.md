Professor: Mário
Sala: 8
Semestre: 1º 
tags: #Eletronica #PrimeiroSemestre #Agosto2026

---

Anotações da Aula:
- Álgebra Booleana
  A Álgebra Booleana é o ramo da matemática e da lógica formal que manipula variáveis capazes de assumir apenas dois valores: Verdadeiro (1) ou Falso (1).
	- Data de Origem
		- Ano de Criação: 1854
		- Criador: George Boole, matemático e filósofo britânico.
		- Marco Histórico: Apresentada na obra _"An Investigation of the Laws of Thought"_ ("Uma Investigação das Leis do Pensamento"), onde Boole sistematizou a lógica aristotélica em uma linguagem matemática abstrata.
	- Principais Conceitos
		- Estados Binários: Todas as variáveis e resultados são restritos a dois estados opostos ($1/0$, $V/F$, $On/Off$).
	- Operadores Fundamentais:
	    - E (AND / $\cdot$): Retorna 1 apenas se todas as entradas forem 1
	    - OU (OR / $+$): Retorna 1 se ao menos uma das entradas for 1
	    - NÃO (NOT / $\neg$ ou $\overline{A}$): Inverte o valor da entrada (0 vira 1, e 1 vira 0)
        
	- Portas Lógicas: Representações físicas ou esquemáticas dos operadores booleanos em circuitos eletrônicos;
	- Tabela Verdade: Matriz que mapeia todas as combinações de entrada possíveis e seus respectivos resultados;
	- Utilidades:
		- Arquitetura de Computadores: Base para o projeto de transistores, microprocessadores, memórias e circuitos integrados;
		- Programação de Software: Construção de desvios condicionais, controle de fluxo e validação de regras de negócio;
		- Bancos de Dados: Filtragem de registros em consultas SQL usando condições combinadas;
		- Sistemas de Controle: Automação industrial, robótica e sistemas de segurança acionados por combinações de sensores;

Conceitos Importantes:
- Aprofundamento de Álgebra Booleana: Portar lógicas
	- Portas lógicas são os componentes físicos básicos (construídos a partir de transistores) que implementam as operações da Álgebra Booleana em circuitos eletrônicos. Elas recebem sinais elétricos de entrada (alta tensão para $1$, baixa tensão para $0$) e produzem uma única saída lógica.
	- Os principais conjuntos estudos serão:
		- Porta AND (E), circuito em série. Para que a corrente passe (saída 1), todas as chaves de entrada precisam estar fechadas (em 1). Se qualquer entrada for $0$, a saída será 0:
		  ![[Pasted image 20260808105356.png]]
		- Porta OR (OU), circuito em paralelo. Se pelo menos uma das chaves for fechada (em 1), a corrente passa (saída 1). A saída só será $0$ se absolutamente todas as entradas forem 0:
		 ![[Pasted image 20260808105458.png]]
		- Porta NOT (NÃO / Inversor), possui apenas uma entrada. Sua função é simplesmente inverter o estado do sinal elétrico recebido:
		  ![[Pasted image 20260808105617.png]]
		- Porta NAND (NÃO-E / "NE"), uma porta AND seguida por um inversor (NOT). A saída resultante é exatamente o inverso do que seria em uma porta AND comum. A saída só vai para  quando todas as entradas forem 1:
		  ![[Pasted image 20260808105735.png]]
		- Porta NOR (NÃO-OU), uma porta OR seguida por um inversor (NOT). A saída resultante é exatamente o inverso do que seria em uma porta OR comum. A saída só vai para 1 se todas as entradas forem 0:
		  ![[Pasted image 20260808105830.png]]
		- Porta XOR (OU Exclusivo), analisa a diferença entre as entradas. Se os valores das entradas forem diferentes entre si, a saída será 1. Se os valores forem iguais (ambos 0 ou ambos 1), a saída será 0:
		  ![[Pasted image 20260808105955.png]]

Indicações do Professor:
- Comprar calculadora cientifica;
- Decorar o Pai Nosso;

Conteúdos Extras/ Pesquisa:
- Álgebra Booleana
	- Livro: Elementos de Eletrônica Digital, de Ivan V. Idoeta e Antonio V. Capuano;
	- Vídeo: Sistemas Digitais, da UNIVESP (Universidade Virtual do Estado de SP). Aulas completas cobrindo Álgebra Booleana, Teoremas de De Morgan, Tabela Verdade e Mapas de Veitch-Karnaugh.
	- Vídeo: Sistemas Digitais, do Curso em Vídeo (Prof. Gustavo Guanabara. Explicações visuais e bem dinâmicas focadas em lógica binária, portas lógicas e fundamentos para programação.


---

Resumo: A aula abordou os fundamentos da Álgebra Booleana e das portas lógicas (AND, OR, NOT, NAND, NOR e XOR), detalhando como o filósofo e matemático George Boole criou essa estrutura em 1854 para trabalhar com estados binários (0 e 1) que formam a base dos circuitos digitais e da computação moderna. Durante a explicação, foram apresentados os símbolos gráficos padronizados, as expressões algébricas e as tabelas verdade completas de cada porta, destacando suas regras de funcionamento, desde o comportamento básico das portas fundamentais até o papel de inversão das portas derivadas (NAND e NOR) e a identificação de diferenças da XOR, além de exemplificar suas aplicações práticas em hardware, programação e sistemas digitais.