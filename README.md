## 1. Caracterização da Organização

- S. A DE LIMA - Manutenção preventiva e corretiva de geradores.
- Com fins lucrativos, a empresa conta com 15 funcionários e 96 clientes fixos, somando uma média de 33 manutenções em geradores de energia por mês. 

- Hoje em dia a empresa não tem um controle digital para a organização dos seus dados em geral, os dados são mantidos de maneira física, em fichas e papéis. Desde as informações dos atendimentos, até às informações dos clientes. 
Com um banco de dados adequado, essas informações ficarão muito mais seguras, além de estarem organizadas e reservadas somente num lugar, facilitando as buscas e consultas. 

- Escolhemos essa organização por conta do caso e das dificuldades, visando que, temos a possibilidade real de implantar esse plano caso tudo ocorra certo. Não escolhemos uma empresa grande nem pequena, visamos também uma empresa com um local acessível para visitas caso necessário, além de conseguirmos contato direto com o dono.

- Endereço da empresa: https://maps.app.goo.gl/XExBHSXrFvbUNv8Y6?g_st=aw
---

## 2. Processos de Negócio

- Cadastro de clientes: preservar as informações dos clientes da empresa. 

- Cadastro de geradores: controlar os geradores supervisionados pela empresa, para manter assertividade nas manutenções. 

- Manutenção: guardar as informações a respeito das manutenções, buscando a organização de todos os processos feitos em um cliente/gerador.

- Serviço: qual tipo de serviço será feito, incluindo valores bases. 

- Técnico: manter um banco de dados com as informações dos técnicos da empresa. 


<img width="569" height="867" alt="fluxogramabanco drawio" src="https://github.com/user-attachments/assets/4c413027-2f30-45d1-9d6c-9ba2a2a3e1d4" />



---

## 3. Requisitos do Sistema


### 3.1 Requisitos Funcionais

O sistema deve cadastrar dados incluindo as informações: nome, CPF/CNPJ, telefone, endereço,e-mail, cidade e estado. Gerador: número de série,marca, modelo, status e potência. Manutenções: data da manutenção, tipo de manutenção, serviço realizado, status e valor. Serviços: nome do serviço,descrição,e valor base. Técnicos:nome, cpf, telefone e email.

O sistema deve permitir o registro de apenas um gerador por número de série, incluindo apenas letras e números.

O sistema deve permitir cadastrar mais de um gerador por cliente, dependendo do porte e necessidade.

O sistema deve permitir que exista apenas um técnico por CPF, sendo digitado apenas com números e tendo tamanho exato de 11 dígitos.

O sistema deve permitir que haja o cadastro de mais de um serviço por cliente. 

O sistema deve cadastrar apenas quando todos os requisitos obrigatórios estiverem preenchidos (estes que foram citados no primeiro requisito funcional)

O sistema deve permitir que uma manutenção tenha mais de um técnico vinculado, a manutenção precisa ser digitada somente em números, pois trata-se de código único e exclusivo.

O sistema deve permitir que o usuário cadastre, consulte e busque os históricos dos clientes.

### 3.2 Requisitos Não Funcionais

Criptografia: todos os dados sensíveis devem ser criptografados, visando a segurança: CPF, endereço, 
valores; Considerar a criptografia desses itens em todos os atributos que coincidirem com as nomenclaturas citadas.

Acessibilidade: o sistema deve se adequar às normas impostas pela WCAG 2.1 nível AA, em todas as páginas.

Tempo de resposta: O sistema deve cadastrar e carregar as respostas em até 5 segundos em todos os dispositivos de acesso.

Portabilidade e Compatibilidade: Quando atualizado, o sistema deve estar compatível com os sistemas operacionais populares, desde sua instalação até as suas atualizações.

Transparência: O programa deve se comportar de maneira acessível, simples e compreensível para todos os usuários.  

## 4. Regras de Negócio

Regras operacionais:
- Toda manutenção deve ter, no mínimo, um serviço vinculado no momento do seu registro; uma manutenção pode envolver mais de um serviço, e o valor final cobrado é a soma dos valores desses serviços.

- Toda manutenção deve ter, no mínimo, um técnico vinculado no momento do seu registro; uma manutenção pode envolver mais de um técnico.

- O gerador necessariamente tem que pertencer a um cliente.

- Dependendo do tipo de manutenção, muda a ordem do pagamento: no caso de uma manutenção corretiva, que impede o funcionamento do gerador, pode haver a troca antes de pagar, mas apenas se o orçamento for confirmado pelo cliente e ele estiver de acordo. Já no caso de uma manutenção preventiva, que não impede o funcionamento do gerador, a manutenção é realizada após o pagamento.

- Os geradores precisam ter um cronograma de inspeção de manutenção preventiva.

- Algumas informações não podem se repetir: são únicas para cada cliente, gerador ou técnico — respectivamente, o CPF/CNPJ, o número de série e o CPF.

Restrições organizacionais:
- Os serviços correspondem e respeitam as normas regulamentadoras NR-10 (elétrica), NR-12 (máquinas), NR-20 (inflamáveis e combustíveis) e NR-6 (EPI), justamente por envolver riscos elétricos, uso de máquinas e manuseio de combustível.

- O sistema não pode ter limite de horário para o registro, devido ao plantão de 24h de atendimento de emergência.

- Peças como bateria, óleo, filtro de ar e tanque têm prazo de troca ou limpeza, o que orienta o cronograma de inspeção preventiva.

---

## 5. Dicionário de Dados Conceitual (Preliminar)
## 5.1 Objetivo
Este documento apresenta o dicionário de dados referente ao Diagrama Entidade-Relacionamento (DER) elaborado para o sistema da empresa escolhida pelo grupo. O sistema tem como finalidade controlar os clientes, os geradores de energia pertencentes a cada cliente, as manutenções realizadas nesses geradores, os técnicos responsáveis e os serviços prestados.

## 5.2 Modelo conceitual
| Entidade |  Relaciona-se com | Cardinalidade |
|----------|----------     |-----------------------|
| Cliente   | Gerador      | 	1:N — um cliente pode ter zero ou vários geradores (0,n); cada gerador pertence a exatamente um cliente (1,1).             
| Gerador   | Manutenção   |  1:N — um gerador pode ter zero ou várias manutenções (0,n); cada manutenção é feita em exatamente um gerador (1,1).             |
| Manutenção| Técnico      | 	N:N — uma manutenção precisa de pelo menos um técnico, podendo ter mais (1,n); um técnico pode participar de zero ou várias manutenções (0,n).             |
| Manutenção| Serviço      | 	N:N — uma manutenção usa pelo menos um serviço, podendo usar mais (1,n); um serviço pode ser usado em zero ou várias manutenções (0,n).              |

Manutenção é a entidade que concentra os dois relacionamentos N:N do modelo — com Técnico e com Serviço — por isso conta com duas tabelas associativas (Manutencao_Tecnico e Manutencao_Servico), que existem só para guardar essas ligações.

Cliente é a pessoa física ou jurídica que contrata os serviços e possui geradores cadastrados. Gerador é o equipamento de geração de energia pertencente a um cliente. Manutenção é o evento de atendimento (preventivo ou corretivo) realizado em um gerador. Técnico é o profissional responsável por executar as manutenções. Serviço é o catálogo de tipos de serviço que podem ser prestados durante uma manutenção.

## 5.3 Fluxo de dados (visão de DFD)
Cliente é cadastrado no sistema → o cliente tem um ou mais geradores vinculados a ele em GERADOR → quando um gerador precisa de atendimento, abre-se um registro em MANUTENÇÃO, ligado a esse gerador → a manutenção é associada a um ou mais técnicos (via MANUTENCAO_TECNICO) e a um ou mais serviços do catálogo SERVIÇO (via MANUTENCAO_SERVICO) → o valor final da manutenção é calculado a partir dos serviços realizados e registrado em MANUTENÇÃO.

Tipos de dado:
|Tipo | Significado | 
|----------|-----------|
|Chave primária| Identifica cada registro de uma tabela de forma exclusiva, sem repetição — é o "RG" daquele registro.|
|Chave estrangeira| É o campo que guarda o valor da chave primária de outra tabela, ligando as duas.|


## CLIENTE 
CLIENTE = @id_cliente + nome + cpf_cnpj + telefone + endereco + email + cidade + estado
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
|id_cliente|Identificador único do cliente no sistema. | Obrigatório; chave primária, gerada automaticamente.|
|nome |	Nome completo (pessoa física) ou razão social (pessoa jurídica) do cliente. Ex.: "Comércio Fictício LTDA".|Obrigatório.|
|cpf_cnpj          | Documento de identificação do cliente (CPF ou CNPJ).          | Obrigatório; deve ser único; dado sensível — armazenado de forma criptografada.   | 
|telefone        | Telefone de contato do cliente.          |     Obrigatório.      | 
|endereco        |  Endereço completo do cliente (rua, número, bairro).         |    Obrigatório.          | 
| email         | 	E-mail de contato do cliente.          |  Obrigatório.            | 
|  cidade        | Cidade onde o cliente está localizado.          |    Obrigatório.          | 
|  estado    |Sigla do estado (ex.: SP).           |    Obrigatório; 2 caracteres.          | 

## GERADOR
GERADOR = @id_gerador + id_cliente + numero_serie + marca + modelo + status + potencia
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
|id_gerador| 	Identificador único do gerador no sistema.    |  Obrigatório; chave primária, gerada automaticamente.     
|id_cliente|  	Indica a qual cliente o gerador pertence.   |  Obrigatório; chave estrangeira referenciando Cliente.   |  
|numero_serie| Número de série de fabricação do gerador.  | Obrigatório; deve ser único — não pode existir mais de um gerador com o mesmo número de série.            |   	                
|marca  |  	Fabricante do gerador. Ex.: "Cummins".    |  Obrigatório.        |  	                  
|modelo   | Modelo do gerador dentro da marca.        |   Obrigatório.          |                     
|status |  	Situação atual do gerador.        |  Obrigatório; valores possíveis: ativo, em manutenção, inativo.          |  	              
|potencia |   	Potência do gerador em kVA.   | Obrigatório; valor numérico positivo.        | 	                    

## MANUTENÇÃO
MANUTENCAO = @id_manutencao + id_gerador + data_manutencao + tipo_manutencao + servico_realizado + status + valor
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_manutencao |  	Identificador único da manutenção.         |  Obrigatório; chave primária, gerada automaticamente.  |  
| id_gerador |  	Indica em qual gerador a manutenção foi realizada.       | Obrigatório; chave estrangeira referenciando Gerador.   | 	  
| data_manutencao  |  Data em que a manutenção foi executada.       |    Obrigatório.          |                     
| tipo_manutencao | 	Classifica a manutenção quanto ao motivo do atendimento.    	     |  Obrigatório; valores possíveis: preventiva, corretiva.     |  
| servico_realizado | 	Descrição do que foi feito no atendimento.        |   Obrigatório.         | 	                      
| status | 	Situação atual da manutenção.        |  Obrigatório; valores possíveis: aberta, em andamento, concluída.   |  	
| valor | 	Valor total cobrado pela manutenção.          | Obrigatório; valor numérico positivo.          | 	 

## TÉCNICO
TECNICO = @id_tecnico + nome + cpf + telefone + email
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_tecnico |  Identificador único do técnico.        |  Obrigatório; chave primária, gerada automaticamente.  	   | 
| nome |  Nome completo do técnico.	        |    Obrigatório.         |
| cpf |  CPF do técnico.        |  	Obrigatório; deve ser único — não pode existir mais de um técnico com o mesmo CPF; dado sensível — armazenado de forma criptografada.           | 
| telefone |  Telefone de contato do técnico.	      |   Obrigatório.       |  
| email | 	E-mail de contato do técnico.        |  Obrigatório.            | 	          

## SERVIÇO
SERVICO = @id_servico + nome_servico + descricao + valor_base
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_servico   | 	Identificador único do serviço no catálogo.  | Obrigatório; chave primária, gerada automaticamente.|  
| nome_servico         | 	Nome do serviço oferecido. Ex.: "Troca de óleo".         |   Obrigatório.       |	
| descricao         |  		Explicação detalhada do que o serviço inclui.       |  Obrigatório.          | 
| valor_base  | 	Valor de referência do serviço, antes de ajustes por manutenção.| Obrigatório; valor numérico positivo.  | 

## MANUTENÇÃO_TÉCNICO
MANUTENCAO_TECNICO = id_manutencao + id_tecnico
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_manutencao   |Referência à manutenção envolvida.          |  Obrigatório; chave estrangeira referenciando Manutenção; compõe a chave primária desta tabela. 	 |    
|  id_tecnico        |	Referência ao técnico envolvido.        |  Obrigatório; chave estrangeira referenciando Técnico; compõe a chave primária desta tabela — permite mais de um técnico por manutenção.       |	

## MANUTENÇÃO_SERVIÇO
MANUTENCAO_SERVICO = id_manutencao + id_servico
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_manutencao   | Referência à manutenção envolvida.         | Obrigatório; chave estrangeira referenciando Manutenção; compõe a chave primária desta tabela.           |    
| id_servico  | 	Referência ao serviço envolvido.        |  Obrigatório; chave estrangeira referenciando Serviço; compõe a chave primária desta tabela — permite mais de um serviço por manutenção.          |  	



## 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
A modelagem conceitual foi elaborada a partir dos processos de negócio, requisitos funcionais e regras de negócios levantados para a empresa. O modelo busca representar as principais informações relacionadas aos clientes, seu geradores, manutenções realizadas, os técnicos envolvidos e os serviços prestados.

### 6.1 Entidades reconhecidas

Foram identificadas cinco entidades principais.

### Cliente

Representa as pessoas físicas ou jurídicas que contratam os serviços da empresa. A entidade armazena  informações necessárias para a identificação e contato com o cliente.

### Gerador

Representa os equipamentos de geração de energia pertencentes aos clientes. A entidade permite controlar informações como número de série, marca, modelo, status e potência.

### Manutenção

Representa o atendimento realizado pela empresa em um determinado gerador. Cada registro de manutenção permite armazenar informações sobre a data, tipo de manutenção, status e valor do atendimento.

### Técnico

Representa os profissionais responsáveis pela execução das manutenções. São armazenadas informações para identificação e contato dos técnicos.

### Serviço

Representa os serviços oferecidos pela empresa e que podem ser utilizados durante uma manutenção, contendo informações como nome, descrição e valor-base.

### 6.2 Atributos e classificações

Os atributos foram definidos de acordo com as informações necessárias para identificar e controlar cada entidade.

Cliente

| Atributo     | Classificação         |
| ------------ | --------------------- |
| `id_cliente` | Identificador         |
| `nome`       | Descritivo            |
| `cpf_cnpj`   | Identificação / único |
| `telefone`   | Contato               |
| `endereco`   | Localização           |
| `email`      | Contato               |
| `cidade`     | Localização           |
| `estado`     | Localização           |

O id_cliente identifica exclusivamente cada cliente. O cpf_cnpj deve ser único e obrigatório. Essas informações já estão definidas no dicionário de dados do projeto.

Gerador

| Atributo       | Classificação         |
| -------------- | --------------------- |
| `id_gerador`   | Identificador         |
| `id_cliente`   | Referência            |
| `numero_serie` | Identificação / único |
| `marca`        | Descritivo            |
| `modelo`       | Descritivo            |
| `status`       | Classificação         |
| `potencia`     | Quantitativo          |

O numero_serie é um identificador único do equipamento, enquanto id_cliente representa sua ligação com o proprietário.

Manutenção

| Atributo            | Classificação |
| ------------------- | ------------- |
| `id_manutencao`     | Identificador |
| `id_gerador`        | Referência    |
| `data_manutencao`   | Temporal      |
| `tipo_manutencao`   | Classificação |
| `servico_realizado` | Descritivo    |
| `status`            | Classificação |
| `valor`             | Quantitativo  |

A entidade registra o atendimento realizado em um gerador e permite diferenciar manutenções preventivas e corretivas.

Técnico

| Atributo     | Classificação         |
| ------------ | --------------------- |
| `id_tecnico` | Identificador         |
| `nome`       | Descritivo            |
| `cpf`        | Identificação / único |
| `telefone`   | Contato               |
| `email`      | Contato               |

O cpf é único para cada técnico, conforme a regra estabelecida para o sistema.

Serviço

| Atributo       | Classificação |
| -------------- | ------------- |
| `id_servico`   | Identificador |
| `nome_servico` | Descritivo    |
| `descricao`    | Descritivo    |
| `valor_base`   | Quantitativo  |

Os atributos permitem identificar o serviço, explicar o que será realizado e estabelecer seu valor de referência.


### 6.3 Relacionamentos pertinentes

Foram identificados quatro relacionamentos principais entre as entidades.

# Cliente — possui — Gerador

Cardinalidade: 1:N

Um cliente pode possuir zero ou vários geradores, enquanto cada gerador pertence obrigatoriamente a um único cliente.

CLIENTE (0,n) ─── possui ─── (1,1) GERADOR

Essa relação representa a regra de negócio de que todo gerador cadastrado deve estar vinculado a um cliente.

# Gerador — recebe — Manutenção

Cardinalidade: 1:N

Um gerador pode receber zero ou várias manutenções durante sua utilização. Cada manutenção, entretanto, deve estar obrigatoriamente relacionada a um único gerador.

GERADOR (0,n) ─── recebe ─── (1,1) MANUTENÇÃO

Essa relação permite manter o histórico de atendimentos realizados em cada equipamento.

# Manutenção — realizada por — Técnico

Cardinalidade: N:N

Uma manutenção pode envolver um ou vários técnicos, enquanto um técnico pode participar de zero ou várias manutenções.

MANUTENÇÃO (1,n) ─── realizada por ─── (0,n) TÉCNICO

A cardinalidade foi definida dessa forma porque o sistema deve permitir que uma mesma manutenção tenha mais de um técnico vinculado.

# Manutenção — utiliza — Serviço

Cardinalidade: N:N

Uma manutenção pode utilizar um ou vários serviços, enquanto um serviço pode ser utilizado em zero ou várias manutenções.

MANUTENÇÃO (1,n) ─── utiliza ─── (0,n) SERVIÇO

Essa relação foi definida porque uma manutenção pode envolver mais de um serviço e o valor final pode ser composto pelos serviços realizados.

### 6.4 Restrições e políticas organizacionais

O modelo conceitual considera as principais regras de negócio identificadas durante o levantamento da empresa.

Todo gerador deve estar vinculado a um cliente.
Toda manutenção deve estar vinculada a um gerador.
O número de série do gerador deve ser único.
O CPF do técnico deve ser único.
Uma manutenção deve possuir pelo menos um técnico.
Uma manutenção deve possuir pelo menos um serviço.
Uma manutenção pode possuir vários técnicos.
Uma manutenção pode possuir vários serviços.
O sistema deve manter o histórico das manutenções realizadas nos geradores.
O tipo de manutenção pode ser preventiva ou corretiva.
Os geradores devem possuir um cronograma de inspeção preventiva.
O atendimento não deve possuir limitação de horário devido ao plantão de 24 horas da empresa.

---

## 7. Diagrama Entidade-Relacionamento (DER)

<img width="2048" height="920" alt="image" src="https://github.com/user-attachments/assets/3235ce75-64c2-42b6-812b-5671296bc9fc" />

---

## 8. Justificativa Técnica
- Entidades: Separamos Cliente, Gerador, Manutenção, Técnico e Serviço porque cada uma tem ciclo de vida próprio — um cliente existe sem gerador, um gerador passa por várias manutenções, um técnico atende várias manutenções, e um serviço é um catálogo reutilizável.Se juntasse manutenção e gerador ficaria duplicando dados a cada manutenção.

- Atributos: Cada atributo ficou na entidade que ele realmente descreve. Dados que variam a cada evento (data, tipo, status, valor) foram para Manutenção; dados fixos do equipamento (marca, modelo, potência) ficaram em Gerador. Os dados do técnico que não entraram direto em manutenção pra evitar que aja redundância e também possibilitar consulta de histórico de cada técnico.

Cardinalidade:
- Cliente–Gerador (0,n)-(1,1): um cliente pode ter vários geradores, mas cada gerador tem só um dono.
  
- Gerador-Manutenção (0,n)-(1,1): um gerador pode ter várias manutenções, mas cada manutenção é sobre um único gerador.
  
- Manutenção–Técnico (1,n)-(0,n): toda manutenção precisa de pelo menos um técnico, e um técnico pode atender várias manutenções.
  
- Manutenção–Serviço (1,n)-(0,n): toda manutenção precisa de ao menos um serviço definido no momento do registro; um serviço pode estar cadastrado no catálogo sem nunca ter sido utilizado, ou ter sido aplicado em várias manutenções.
  
---

## 9. Uso de Inteligência Artificial
| Item | Registro |
|------|------------------|
| Ferramenta e etapa 1 | Gemini Flash, usada durante a etapa de levantamento dos Requisitos Não Funcionais (RNF) do sistema de controle de geradores e manutenções.|
| *Motivação* | Precisávamos de ajuda para acrescentar mais alguns Requisitos Não Funcionais para compor o dicionário de dados e utilizamos a IA como um ponto de partida. O objetivo foi identificar quais categorias de RNF são mais comuns, como desempenho, segurança e disponibilidade, além de obter exemplos de como esses requisitos poderiam ser descritos. |
| *Prompt(s) utilizados* | "Cite alguns Requisitos Não Funcionais"|
| *Resposta recebida* | A IA explicou que os Requisitos Não Funcionais estão relacionados à forma como o sistema deve funcionar, estabelecendo características, restrições e critérios de qualidade, em vez de descrever funcionalidades específicas. Em seguida, apresentou algumas categorias e exemplos. Entre elas, foram citadas Desempenho e Eficiência, com exemplos relacionados ao tempo de resposta e à capacidade de processamento do sistema, e Segurança, com exemplos como a criptografia de dados sensíveis e a utilização de autenticação de dois fatores (2FA). A resposta também mencionava uma terceira categoria, relacionada à disponibilidade, mas essa parte não chegou a ser analisada completamente	 |
| *Fontes consultadas e verificadas* | Não foram utilizadas fontes externas. As informações vieram do próprio material produzido pelo grupo, com base na visita e na pesquisa de campo realizadas na empresa. |
| *Trechos rejeitados ou corrigidos* | Os exemplos numéricos relacionados ao desempenho, como o tempo de resposta de até 2 segundos e o processamento de 1.000 transações por segundo, foram ajustados. Esses valores eram genéricos e não representavam a realidade da empresa estudada, que possui 96 clientes fixos e uma média de 33 manutenções por mês.	 |
| *Justificativa da escolha final* |Decidimos aproveitar as categorias sugeridas pela IA, principalmente desempenho/eficiência e segurança, pois elas são importantes para o sistema que está sendo desenvolvido. Porém, os exemplos foram adaptados de acordo com a realidade da empresa. Também foram incluídos requisitos relacionados à segurança dos dados e à autenticação. |
| *Reflexão crítica* | O uso da IA ajudou a ter uma ideia inicial de quais Requisitos Não Funcionais poderiam ser utilizados no sistema. Porém, percebemos que nem todos os exemplos apresentados serviam para a realidade da empresa, principalmente os valores relacionados ao desempenho. Por isso, foi necessário analisar as sugestões e fazer as adaptações. Com isso, entendemos que a IA é uma boa ferramenta para ajudar no desenvolvimento do trabalho, mas não devemos aceitar tudo o que ela apresenta sem verificar. É importante usar nosso próprio conhecimento e considerar as necessidades reais da empresa.	|

| Item | Registro |
|------|------------------|
| Ferramenta e etapa 2 |Claude, utilizada como apoio para organizar o dicionário de dados (DER) de acordo com o modelo apresentado. |
| *Motivação* | Organizar as informações do rascunho no formato do exemplo solicitado. |
| *Prompt(s) utilizados* | "Poderia me ajudar a revisar o arquivo".|
| *Resposta recebida* | 	Documento reorganizado com tabelas de atributos, descrição, e regra de negócio associada. |
| *Fontes consultadas e verificadas* | Não foram utilizadas fontes externas. As informações vieram do próprio material produzido pelo grupo, com base na visita e na pesquisa de campo realizadas na empresa.|
| *Trechos rejeitados ou corrigidos* | Decidimos retirar as partes de “Log de acesso” e “Conformidade com a LGPD” que apareciam no exemplo. Essas seções estavam mais relacionadas ao caso apresentado no modelo, que envolvia dados sensíveis de saúde, e não eram necessárias para o projeto da empresa escolhida. |
| *Justificativa da escolha final* | A estrutura do exemplo foi aproveitada porque atendia ao formato solicitado, mas algumas partes foram retiradas para que o documento ficasse adequado ao contexto da empresa e às informações levantadas. |
| *Reflexão crítica* | 	O exemplo ajudou bastante na organização das informações, mas foi necessário analisar o que realmente se aplicava ao projeto. Dessa forma, utilizamos apenas o modelo como referência e fizemos as adaptações necessárias ao próprio trabalho. |

| Item | Registro |
|------|------------------|
| Ferramenta e etapa 3 | Claude, utilizada durante a elaboração da etapa das regras de negócio, para a realização de correções gramaticais do conteúdo.  |
| *Motivação* | Correção do texto contido na etapa 4 (Regras de negócio). |
| *Prompt(s) utilizados* |  [Problema]: O texto pode conter erros.<br>[Condição]: Pode ter qualquer estilo.<br>[Desafio]: Corrigir sem alterar o sentido.<br>[Tarefa]: Corrija gramática, ortografia, pontuação e acentuação, mantendo o estilo original. Retorne apenas o texto corrigido. |
| *Resposta recebida* | Texto corrigido e mantendo concordância e as regras gramáticais. |
| *Fontes consultadas e verificadas* | Não foram utilizadas fontes externas. As informações vieram do próprio material produzido pelo grupo, com base na visita e na pesquisa de campo realizadas na empresa. |
| *Trechos rejeitados ou corrigidos* | Foi decidido inserir a parte "justamente por envolver riscos elétricos, uso de máquinas e manuseio de combustível.", justamente pra existir uma justificativa dessa restrições organizacionais |
| *Justificativa da escolha final* | A IA analisa os detalhes do texto para realizar as correções necessárias |
| *Reflexão crítica* | A correção foi prática e eficaz, porém foi necessário conferir as informações e analisar se era necessário realizar alguma alteração ou adicionar alguma informação. |

| Item | Registro |
|------|------------------|
| Ferramenta e etapa 4 | ChatGPT, utilizado como apoio durante a etapa de Modelagem Conceitual do sistema de controle de geradores e manutenções.|
| *Motivação* |  Tivemos dificuldade para organizar as entidades, seus atributos e principalmente as cardinalidades dos relacionamentos entre Cliente, Gerador, Manutenção, Técnico e Serviço. Utilizamos a IA como apoio para revisar a estrutura que já havia sido definida pelo grupo e verificar se os relacionamentos estavam de acordo com os requisitos e regras de negócio levantados. |
| *Prompt(s) utilizados* | “Com base nos requisitos, regras de negócio e dicionário de dados do projeto, ajude a identificar as entidades, atributos, relacionamentos e cardinalidades da modelagem conceitual.” |
| *Resposta recebida* | A IA organizou as principais entidades do sistema e explicou os relacionamentos entre elas. Foi indicado que Cliente e Gerador possuem uma relação 1:N, Gerador e Manutenção possuem uma relação 1:N, enquanto Manutenção e Técnico e Manutenção e Serviço possuem relações N:N. Também foram apresentadas justificativas para as cardinalidades com base nas regras de negócio.	 |
| *Fontes consultadas e verificadas* |Não foram utilizadas fontes externas. As informações vieram do próprio material produzido pelo grupo, com base na visita e na pesquisa de campo realizadas na empresa.|
| *Trechos rejeitados ou corrigidos* | 	Algumas sugestões da IA foram analisadas e não foram utilizadas diretamente, principalmente sugestões relacionadas à criação de entidades associativas. Como o objetivo dessa etapa era representar o modelo conceitual, mantivemos os relacionamentos N:N entre Manutenção e Técnico e entre Manutenção e Serviço conforme a estrutura adotada pelo grupo. |
| *Justificativa da escolha final* | A IA foi utilizada apenas como apoio para revisar e organizar o modelo. A decisão final sobre as entidades, atributos e cardinalidades foi feita pelo grupo, considerando os requisitos e as regras de negócio da empresa estudada. |
| *Reflexão crítica* | A utilização da IA ajudou principalmente a visualizar possíveis problemas na modelagem e entender melhor as cardinalidades. Porém, percebemos que uma sugestão gerada automaticamente não deve ser aplicada sem análise. Foi necessário comparar as sugestões com as regras de negócio e com o modelo que já havia sido desenvolvido pelo grupo. Dessa forma, a IA serviu como ferramenta de apoio e revisão, e não como responsável pela definição final do modelo.	|
