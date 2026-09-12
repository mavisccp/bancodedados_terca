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

## 5. Dicionário de Dados Conceitual 
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

## 5.4 Convenções do dicionário
Notação formal: = é composto de · + conecta elementos obrigatórios · ( ) elemento opcional · @ identificador (chave primária)
## Tipos de dado:
|Tipo |  Significado | 
|----------|----------|
|INT |Número inteiro, sem casas decimais. Usado principalmente nos campos de identificação (id) de cada tabela|
|VARCHAR(n) | Texto de tamanho variável, onde n é a quantidade máxima de caracteres aceitos. Usado para nomes, e-mails, endereços e documentos | 
|DATE | Data no formato dia/mês/ano|
|DECIMAL(p,e) | Número com casas decimais, onde p é o total de dígitos e e é a quantidade deles depois da vírgula. Usado para valores em dinheiro e para a potência do gerador | 
|PK (chave primária) | Identifica cada registro de uma tabela de forma exclusiva, sem repetição é o "RG" daquele registro |
|FK (chave estrangeira) | É o campo que guarda o valor da chave primária de outra tabela, ligando as duas | 

## Dicionário de dados por entidade
## CLIENTE 
CLIENTE = @id_cliente + nome + cpf_cnpj + telefone + endereco + email + cidade + estado
| Atributo | Tipo físico | Obrigatório| Significado e relevância|
|----------|-----------|------------------------------|------------------------------|
|id_cliente| INT |  Sim (PK) |Identifica um cliente de forma exclusiva dentro do sistema; usado para localizar aquele cliente específico|
|nome | VARCHAR(100)|Sim |Nome completo (pessoa física) ou razão social (pessoa jurídica) do cliente|
| cpf_cnpj| VARCHAR(14)|Sim |Documento de identificação (CPF ou CNPJ). Armazenado como texto porque pode começar com zero e não entra em cálculos matemáticos|
|telefone| VARCHAR(15)|Sim| Número de telefone para contato com o cliente|
| endereço | VARCHAR(150) |Sim |Endereço completo (rua, número, bairro) onde o cliente está localizado|
|email| VARCHAR(100) |Sim| 	Endereço de e-mail usado para contato com o cliente|
| cidade | VARCHAR(50) | Sim |	Cidade onde o cliente reside ou está registrado|
|estado |	VARCHAR(2)|Sim| Sigla do estado brasileiro (ex.: SP, RJ, MG)|

## GERADOR
GERADOR = @id_gerador + id_cliente + numero_serie + marca + modelo + status + potencia
| Atributo | Tipo físico | Obrigatório| Significado e relevância|
|----------|-----------|--------------|-------------------------|
|id_gerador|   	INT        |   Sim (PK)           | 	Identifica um gerador de forma exclusiva dentro do sistema                        |
|id_cliente|    INT       |     	Sim (FK)         |  	Indica a qual cliente aquele gerador pertence; liga a tabela Gerador à tabela Cliente                       |
|numero_serie|    VARCHAR(30)       |     	Sim         |   	Número de série de fabricação do gerador, gravado pelo fabricante                      |
|marca  | VARCHAR(50)     |    	Sim          |  	Nome do fabricante do gerador (ex.: Caterpillar, Cummins                       |
|modelo   |  	VARCHAR(50)         |    	Sim          |  Modelo específico do gerador dentro da marca                       |
|status | VARCHAR(20)          |      Sim        |  	Situação atual do gerador (ex.: ativo, em manutenção, inativo)                       |
|potencia |  DECIMAL(8,2)         |        Sim      | 	Potência do gerador em kVA, indicando a capacidade de energia gerada                        |

## MANUTENÇÃO
MANUTENCAO = @id_manutencao + id_gerador + data_manutencao + tipo_manutencao + servico_realizado + status + valor
| Atributo | Tipo físico | Obrigatório| Significado e relevância|
|----------|-----------|--------------|-------------------------|
| id_manutencao |    INT       |    	Sim (PK)          |    Identifica uma manutenção de forma exclusiva                  |
| id_gerador |   	INT        |      	Sim (FK)        | 	Indica em qual gerador aquela manutenção foi realizada; liga a tabela Manutenção à tabela Gerador                        |
| data_manutencao  |      DATE     |     	Sim         |  	Data em que a manutenção foi executada                       |
| tipo_manutencao |     	VARCHAR(30)      |      	Sim        | 	Classifica a manutenção como preventiva ou corretiva                        |
| servico_realizado |  VARCHAR(200)         |      	Sim        | 	Descrição do que foi efetivamente feito no atendimento (troca de peça, limpeza, ajuste etc.)                        |
| status | VARCHAR(20)          |       	Sim       |  	Situação atual da manutenção (ex.: aberta, em andamento, concluída)                       |
| valor | 	DECIMAL(10,2)          |      	Sim        | 	Valor total cobrado pela manutenção realizada                        |


|  |           |              |                         |
|  |           |              |                         |
|  |           |              |                         |
|  |           |              |                         |
|  |           |              |                         |





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
