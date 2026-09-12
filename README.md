## 1. Caracterização da Organização

- S. A DE LIMA - Manutenção preventiva e corretiva de geradores.
- Com fins lucrativos, a empresa conta com 15 funcionários e 96 clientes fixos, somando uma média de 33 manutenções em geradores de energia por mês. 

- Hoje em dia a empresa não tem um controle digital para a organização dos seus dados em geral, os dados são mantidos de maneira física, em fichas e papéis. Desde as informações dos atendimentos, até às informações dos clientes. 
Com um banco de dados adequado, essas informações ficaram muito mais seguras, além de estarem organizadas e reservadas somente num lugar, facilitando as buscas e consultas. 

- Escolhemos essa organização por conta do caso e das dificuldades, visando que, temos a possibilidade de realmente implantar esse plano caso tudo ocorra certo. Não escolhemos uma empresa grande e nem pequena, visamos também uma empresa com um local acessível para visitas caso necessário, além de conseguirmos contato direto com o dono.

- Endereço da empresa: https://maps.app.goo.gl/XExBHSXrFvbUNv8Y6?g_st=aw
---

## 2. Processos de Negócio

- Cadastro de clientes: preservar as informações dos clientes da empresa. 

- Cadastro de geradores: controlar os geradores supervisionados pela empresa, para manter assertividade nas manutenções 

- Manutenção: guardar as informações a respeito das manutenções, buscando a organização de todos os processos feitos em um cliente/gerador

- Serviço: qual tipo de serviço será feito, incluindo valores bases. 

- Técnico: manter um banco de dados com as informações dos técnicos da empresa. 


- *Fluxogramas:* (Opcional) represente visualmente pelo menos os processos-chave (imagens anexadas). Deve ficar claro o fluxo de cada processo e como eles se integram entre si.
(verificar se iremos fazer)

---

## 3. Requisitos do Sistema


### 3.1 Requisitos Funcionais

O sistema deve cadastrar clientes, geradores, manutenções, serviços e técnicos. 

O sistema deve permitir o registro de apenas um gerador por número de série.

O sistema deve permitir cadastrar mais de um gerador por cliente, dependendo do porte e necessidade.

O sistema deve permitir que exista apenas um técnico por CPF.

O sistema deve permitir que haja o cadastro de mais de um serviço por cliente. 

O sistema deve cadastrar apenas quando todos os requisitos obrigatórios estiverem preenchidos.

O sistema deve permitir que mais de um técnico esteja em apenas uma manutenção. 

O sistema deve permitir que o usuário cadastre, consulte e busque os históricos dos clientes.

### 3.2 Requisitos Não Funcionais

Criptografia: todos os dados sensíveis devem ser criptografados, visando a segurança. 

Acessibilidade: o sistema deve ser adequar as normas impostas pela WCAG 2.1 nível AA.

Tempo de resposta: O sistema deve cadastrar e carregar as respostas em até 5 segundos.

Portabilidade e Compatibilidade: Quando atualizado, o sistema deve estar compatível com os sistemas operacionais populares. 

Transparência: O programa deve ser comportar de maneira acessível, simples e compreensível para todos os usuários.  

## 4. Regras de Negócio
(esta seção DIVIDE com a Seção 3 "Requisitos do Sistema" os mesmos 7,5% da dimensão conceitual — juntas valem 7,5%, não 7,5% cada — + 4% exclusivos desta seção na documentação. "Regras de negócio" é o termo técnico usado em modelagem de dados para as regras de funcionamento de qualquer organização, com ou sem fins lucrativos)

- *Regras operacionais:* condições que a organização impõe (ex.: "um pedido só pode ser fechado se houver estoque disponível", "uma doação só pode ser registrada com identificação do doador", "um ritual só pode ser agendado se o espaço estiver disponível").
- *Restrições organizacionais:* limitações que afetam o modelo (ex.: políticas internas, prazos, exigências legais, normas religiosas ou estatutárias) — e por que elas importam.

---
## 5. Dicionário de Dados Conceitual (Preliminar)
## 5.1 Objetivo
Este documento apresenta o dicionário de dados referente ao Diagrama Entidade-Relacionamento (DER) elaborado para o sistema da empresa escolhida pelo grupo. O sistema tem como finalidade controlar os clientes, os geradores de energia pertencentes a cada cliente, as manutenções realizadas nesses geradores, os técnicos responsáveis e os serviços prestados.

## 5.2 Modelo conceitual
| Entidade |  Relaciona-se com | Cardinalidade |
|----------|----------     |-----------------------|
| Cliente   | Gerador      | 	1:N — um cliente pode ter zero ou vários geradores (0,n); cada gerador pertence a exatamente um cliente (1,1)             
| Gerador   | Manutenção   |  1:N — um gerador pode ter zero ou várias manutenções (0,n); cada manutenção é feita em exatamente um gerador (1,1)             |
| Manutenção| Técnico      | 	1:N — um gerador pode ter zero ou várias manutenções (0,n); cada manutenção é feita em exatamente um gerador (1,1)              |
| Manutenção| Serviço      | 	N:N — uma manutenção usa pelo menos um serviço, podendo usar mais (1,n); um serviço pode ser usado em zero ou várias manutenções (0,n)              |

Manutenção é a entidade que concentra os dois relacionamentos N:N do modelo — com Técnico e com Serviço — por isso conta com duas tabelas associativas (Manutencao_Tecnico e Manutencao_Servico), que existem só para guardar essas ligações.

Cliente é a pessoa física ou jurídica que contrata os serviços e possui geradores cadastrados. Gerador é o equipamento de geração de energia pertencente a um cliente. Manutenção é o evento de atendimento (preventivo ou corretivo) realizado em um gerador. Técnico é o profissional responsável por executar as manutenções. Serviço é o catálogo de tipos de serviço que podem ser prestados durante uma manutenção.

## 5.3 Fluxo de dados (visão de DFD)
Cliente é cadastrado no sistema → o cliente tem um ou mais geradores vinculados a ele em GERADOR → quando um gerador precisa de atendimento, abre-se um registro em MANUTENÇÃO, ligado a esse gerador → a manutenção é associada a um ou mais técnicos (via MANUTENCAO_TECNICO) e a um ou mais serviços do catálogo SERVIÇO (via MANUTENCAO_SERVICO) → o valor final da manutenção é calculado a partir dos serviços realizados e registrado em MANUTENÇÃO.

Tipos de dado:
|Tipo | Significado | 
|----------|-----------|
|Chave primária| Identifica cada registro de uma tabela de forma exclusiva, sem repetição — é o "RG" daquele registro|
|Chave estrangeira| É o campo que guarda o valor da chave primária de outra tabela, ligando as duas|


## CLIENTE 
CLIENTE = @id_cliente + nome + cpf_cnpj + telefone + endereco + email + cidade + estado
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
|id_cliente|Identificador único do cliente no sistema | Obrigatório; chave primária, gerada automaticamente|
|nome |	Nome completo (pessoa física) ou razão social (pessoa jurídica) do cliente. Ex.: "Comércio Fictício LTDA"|Obrigatório|
|cpf_cnpj          | Documento de identificação do cliente (CPF ou CNPJ)          | Obrigatório; deve ser único; dado sensível — armazenado de forma criptografada   | 
|telefone        | Telefone de contato do cliente          |     Obrigatório      | 
|endereco        |  Endereço completo do cliente (rua, número, bairro)         |    Obrigatório          | 
| email         | 	E-mail de contato do cliente          |  Obrigatório            | 
|  cidade        | Cidade onde o cliente está localizado          |    Obrigatório          | 
|  estado    |Sigla do estado (ex.: SP)           |    Obrigatório; 2 caracteres          | 

## GERADOR
GERADOR = @id_gerador + id_cliente + numero_serie + marca + modelo + status + potencia
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
|id_gerador| 	Identificador único do gerador no sistema         |  Obrigatório; chave primária, gerada automaticamente.     
|id_cliente|  	Indica a qual cliente o gerador pertence      |  Obrigatório; chave estrangeira referenciando Cliente   |  
|numero_serie|  	Indica a qual cliente o gerador pertence         | Obrigatório; deve ser único — não pode existir mais de um gerador com o mesmo número de série            |   	                
|marca  |  	Fabricante do gerador. Ex.: "Cummins"    |  Obrigatório        |  	                  
|modelo   | Modelo do gerador dentro da marca        |   Obrigatório          |                     
|status |  	Situação atual do gerador        |  Obrigatório; valores possíveis: ativo, em manutenção, inativo          |  	              
|potencia |   	Potência do gerador em kVA       | Obrigatório; valor numérico positivo        | 	                    

## MANUTENÇÃO
MANUTENCAO = @id_manutencao + id_gerador + data_manutencao + tipo_manutencao + servico_realizado + status + valor
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_manutencao |  	Identificador único da manutenção         |  Obrigatório; chave primária, gerada automaticamente  |  
| id_gerador |  	Indica em qual gerador a manutenção foi realizada       | Obrigatório; chave estrangeira referenciando Gerador   | 	  
| data_manutencao  |  Data em que a manutenção foi executada       |    Obrigatório          |                     
| tipo_manutencao | 	Classifica a manutenção quanto ao motivo do atendimento    	     |  Obrigatório; valores possíveis: preventiva, corretiva     |  
| servico_realizado | 	Descrição do que foi feito no atendimento        |   Obrigatório         | 	                      
| status | 	Situação atual da manutenção        |  Obrigatório; valores possíveis: aberta, em andamento, concluída   |  	
| valor | 	Valor total cobrado pela manutenção          | Obrigatório; valor numérico positivo          | 	 

## TÉCNICO
TECNICO = @id_tecnico + nome + cpf + telefone + email
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_tecnico |  Identificador único do técnico        |  Obrigatório; chave primária, gerada automaticamente  	   | 
| nome |  Nome completo do técnico	        |    Obrigatório         |
| cpf |  CPF do técnico        |  	Obrigatório; deve ser único — não pode existir mais de um técnico com o mesmo CPF; dado sensível — armazenado de forma criptografada           | 
| telefone |  Telefone de contato do técnico	      |   Obrigatório       |  
| email | 	E-mail de contato do técnico        |  Obrigatório            | 	          

## SERVIÇO
SERVICO = @id_servico + nome_servico + descricao + valor_base
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_servico   | 	Identificador único do serviço no catálogo  | Obrigatório; chave primária, gerada automaticamente|  
| nome_servico         | 	Nome do serviço oferecido. Ex.: "Troca de óleo"         |   Obrigatório       |	
| descricao         |  		Explicação detalhada do que o serviço inclui       |  Obrigatório          | 
| valor_base  | 	Valor de referência do serviço, antes de ajustes por manutenção.| Obrigatório; valor numérico positivo  | 

## MANUTENCAO_TECNICO
MANUTENCAO_TECNICO = id_manutencao + id_tecnico
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_manutencao   |Referência à manutenção envolvida          |  Obrigatório; chave estrangeira referenciando Manutenção; compõe a chave primária desta tabela 	 |    
|  id_tecnico        |	Referência ao técnico envolvido        |  Obrigatório; chave estrangeira referenciando Técnico; compõe a chave primária desta tabela — permite mais de um técnico por manutenção       |	

## MANUTENCAO_SERVICO
MANUTENCAO_SERVICO = id_manutencao + id_servico
| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| id_manutencao   | Referência à manutenção envolvida         | Obrigatório; chave estrangeira referenciando Manutenção; compõe a chave primária desta tabela           |    
| id_servico  | 	Referência ao serviço envolvido         |  Obrigatório; chave estrangeira referenciando Serviço; compõe a chave primária desta tabela — permite mais de um serviço por manutenção          |  	











## 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
(vale 7,5% na dimensão conceitual)

- *Entidades reconhecidas:* liste e justifique brevemente cada uma.
- *Atributos e classificações:* quais atributos pertencem a cada entidade.
- *Relacionamentos pertinentes:* como as entidades se conectam.
- *Restrições e políticas organizacionais aplicadas ao modelo.*

---

## 7. Diagrama Entidade-Relacionamento (DER)
(vale 20% — é o item de maior peso da entrega)

- Anexe o DER (em imagem).
- O diagrama deve representar corretamente:
  - Entidades
  - Atributos
  - Relacionamentos
  - *Cardinalidades*
- O modelo deve ser *consistente* e já demonstrar potencial de *escalabilidade e integração* (pensando nas próximas etapas do projeto).

---

## 8. Justificativa Técnica
(vale 7,5% — sozinho, é o subcritério de maior peso dentro da Dimensão Conceitual)

Explique e defenda as decisões de abstração e modelagem tomadas: por que essas entidades, esses atributos, esses relacionamentos e essas cardinalidades — e não outras alternativas possíveis?

---

## 9. Uso de Inteligência Artificial
(documentação obrigatória — não é opcional se o grupo usou IA em qualquer etapa: pesquisa, escrita, organização de ideias ou revisão de texto)

Se o grupo usou alguma ferramenta de IA (ChatGPT, Claude, Gemini, Perplexity etc.) em qualquer parte do trabalho, registre *para cada uso relevante*:

| Item | O que registrar |
|------|------------------|
| *Ferramenta e etapa* | Qual IA foi usada e em qual parte do trabalho (ex.: pesquisa sobre o setor da organização, redação do README, organização dos requisitos, revisão ortográfica/gramatical). |
| *Motivação* | Por que o grupo recorreu à IA nesse ponto específico. |
| *Prompt(s) utilizados* | Texto exato (ou muito próximo) do que foi perguntado/pedido à IA. |
| *Resposta recebida* | Resumo ou trecho relevante da resposta da IA. |
| *Fontes consultadas e verificadas* | Se a IA citou fontes/dados, quais foram checadas pelo grupo e como (ex.: comparação com o que foi observado na visita de campo). |
| *Trechos rejeitados ou corrigidos* | O que da resposta da IA foi descartado, editado ou corrigido manualmente, e por quê. |
| *Justificativa da escolha final* | Por que o grupo manteve, adaptou ou rejeitou o que a IA sugeriu. |
| *Reflexão crítica* | Limites, vieses ou erros identificados no uso da IA nessa etapa (ex.: informação desatualizada, alucinação, generalização incorreta sobre o tipo de organização). |

Se o grupo não usou nenhuma ferramenta de IA, declare isso explicitamente nesta seção.
