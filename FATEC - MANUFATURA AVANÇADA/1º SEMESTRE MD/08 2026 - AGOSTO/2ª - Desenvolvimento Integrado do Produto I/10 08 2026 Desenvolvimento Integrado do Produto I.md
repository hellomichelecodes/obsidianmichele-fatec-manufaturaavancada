Professor: Rafael
Sala: Laboratório 15
Semestre: 1º 
tags: #DesenvolvimentoIntegradoDoProdutoI #PrimeiroSemestre #Agosto2026

---

- # Sobre My SQL
	O **MySQL** foi criado originalmente pelos desenvolvedores **Michael "Monty" Widenius** (finlandês) e **David Axmark** (sueco), junto com o empresário Allan Larsson, fundadores da empresa sueca **MySQL AB**.
	
	**Formação e qualificações dos criadores:**
	- **Michael "Monty" Widenius:** Estudou Ciência da Computação na Universidade de Tecnologia de Helsinque (HUT), na Finlândia, embora tenha deixado a universidade antes de se formar para trabalhar no setor de software. É o autor principal do código original do banco de dados.
	- **David Axmark:** Autodidata em programação e sistemas, atuou no desenvolvimento de software desde o início da década de 1980, sem foco em títulos acadêmicos formais, sendo reconhecido pelo pioneirismo no ecossistema de software livre.
	
	**Cronologia do Desenvolvimento**
	
	- **1994:** Início do desenvolvimento da primeira versão.
	- **23 de maio de 1995:** Lançamento da primeira versão interna do MySQL.
	- **2000:** Adoção da licença de código aberto (GPL), impulsionando sua popularização mundial.
	- **2008 / 2010:** A empresa MySQL AB foi adquirida pela Sun Microsystems em 2008, que por sua vez foi comprada pela **Oracle Corporation** em 2010 (que detém o MySQL até hoje).
	
	- **Principais Aplicações**
		- **Aplicações Web e CMS:** Plataformas como WordPress, Joomla e Drupal utilizam o MySQL como padrão.
		- **Sistemas de E-commerce:** Gerenciamento de catálogos de produtos, clientes e carrinhos de compras.
		- **Serviços em Nuvem e SaaS:** Armazenamento de dados para plataformas de software como serviço.
		- **Arquiteturas LAMP:** Componente fundamental da famosa pilha de desenvolvimento web (Linux, Apache, MySQL, PHP/Python/Perl).
	
	- **Uso Hoje em Dia** 
		Atualmente, o MySQL é o **banco de dados relacional de código aberto mais popular do mundo**. Ele opera em um modelo híbrido sob a tutela da Oracle (oferecendo uma versão comunitária gratuita sob licença GPL e versões comerciais pagas para corporações). É amplamente utilizado desde servidores locais em pequenos projetos até infraestruturas gerenciadas em nuvem como Amazon RDS, Google Cloud SQL e Azure Database for MySQL.
	
	- **Exemplo Prático de Aplicação**
		-  Considere o sistema de cadastro e autenticação de um aplicativo:
			- Criação da tabela de usuários
				
				CREATE TABLE usuarios (
			    id INT AUTO_INCREMENT PRIMARY KEY,
			    nome VARCHAR(100) NOT NULL,
			    email VARCHAR(100) UNIQUE NOT NULL,
			    senha_hash VARCHAR(255) NOT NULL,
			    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
				);
			- Inserção de um registro no momento do cadastro
				INSERT INTO usuarios (nome, email, senha_hash) 
				VALUES ('Ana Silva', 'ana@email.com', 'e10adc3949ba59abbe56e057f20f883e');
			-  Consulta feita pelo aplicativo durante a tela de Login
				SELECT id, senha_hash FROM usuarios WHERE email = 'ana@email.com';
	
	- Conceitos Importantes:
		Para dominar os fundamentos do MySQL e se dar bem na disciplina de Desenvolvimento Integrado de Projeto, os conceitos essenciais que você precisa conhecer são:
		- **1. Arquitetura Relacional e Estrutura**
			- **Banco de Dados Relacional (RDBMS):** Organiza os dados em tabelas compostas por linhas (registros/tuplas) e colunas (campos/atributos) que se relacionam entre si.
			- **Tabelas (Tables):** As estruturas onde os dados são armazenados de fato.
			- **Tipos de Dados (Data Types):** Definem que tipo de informação cada coluna aceita, como `INT` (números inteiros), `VARCHAR` (textos), `DATE/TIMESTAMP` (datas/horários) e `BOOLEAN` (verdadeiro/falso).
		- **2. Integridade e Chaves**
			- **Chave Primária (Primary Key - PK):** Um identificador único para cada registro na tabela (ex: o `id` de um usuário). Não pode haver dois registros com a mesma PK, nem valores nulos.
			- **Chave Estrangeira (Foreign Key - FK):** Um campo que conecta uma tabela à chave primária de outra, garantindo a **integridade referencial** entre os dados (ex: o `id_usuario` dentro de uma tabela de `pedidos`).
			- **Restrições (Constraints):** Regras aplicadas às colunas, como `NOT NULL` (campo obrigatório), `UNIQUE` (não permite valores duplicados) e `DEFAULT` (define valor padrão).
		- **3. Linguagem SQL e Operações**
			- **CRUD:** Acrônimo para as quatro operações fundamentais em qualquer sistema:
			    - **C**reate (`INSERT`) — Criar dados.
			    - **R**ead (`SELECT`) — LER/consultar dados.
			    - **U**pdate (`UPDATE`) — Atualizar dados existentes.
			    - **D**elete (`DELETE`) — Apagar dados.
			- **Filtros e Cláusulas:** Usados para refinar consultas, como `WHERE` (filtrar condições), `ORDER BY` (ordenar resultados) e `GROUP BY` (agrupar dados para cálculos).
			- **Junções (JOINs):** Comandos (`INNER JOIN`, `LEFT JOIN`, etc.) que permitem combinar dados de duas ou mais tabelas relacionáveis em uma única consulta.
		- **4. Performance e Confiabilidade**
			- **Índices (Indexes):** Estruturas internas que aceleram a busca de dados em tabelas grandes (similar ao índice remissivo de um livro).
			- **Transações e Propriedades ACID:** Mecanismos que garantem que uma série de operações SQL ocorra com total sucesso ou seja completamente cancelada (`ROLLBACK`), mantendo o banco seguro contra falhas.

- # Conteúdos Extras/ Pesquisa:
	- Vídeo aula: https://www.youtube.com/watch?v=Ofktsne-utM

---

Resumo: O MySQL é um sistema de gerenciamento de banco de dados relacional lançado em 1995 por desenvolvedores nórdicos. Ele organiza dados em tabelas estruturadas usando a linguagem SQL. Destaca-se pela rapidez, simplicidade e gratuidade, tornando-se a espinha dorsal de boa parte da Web moderna (usado por gigantes como Facebook, Twitter/X e Netflix), sendo mantido hoje pela Oracle.