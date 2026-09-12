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
(vale 10% — Dimensão Procedimental - Segue o modelo do arquivo 02-03g_Exemplo_Dicionario_Dados.pdf)

Para cada entidade identificada, liste:

| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| nome do atributo | o que ele representa | se houver alguma regra (obrigatoriedade, valores possíveis, etc.) |

Mantenha o dicionário organizado e padronizado (mesmo formato de tabela para todas as entidades).

*Atenção à privacidade:* se forem usados exemplos de valores para ilustrar os atributos, esses exemplos devem ser *fictícios* — não utilize dados reais de clientes, fiéis, beneficiários, doadores ou funcionários da organização (nomes, CPFs, contatos etc.), mesmo que tenham sido observados durante a pesquisa de campo. Os exemplos devem apenas ser *coerentes com as operações reais* observadas.

---

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
