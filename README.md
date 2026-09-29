# tech-brain
Tech Brain — Central de conhecimento e estudos sobre Python, SQL, APIs, Git e automação com N8N.

# 🧠 Tech Brain

> Caderno Temático de Tecnologia utilizando Inteligência Artificial como ferramenta de aprendizagem ativa.


## 📌 Sobre o projeto

O **Tech Brain** é um Caderno Temático desenvolvido como parte de um desafio prático, utilizando o **NotebookLM** como ferramenta de apoio à aprendizagem, organização e consolidação do conhecimento.

A proposta é reunir e conectar conceitos fundamentais da área de tecnologia, explorando principalmente:

* 🐍 Python
* 🔗 APIs e APIs REST
* 🗄️ SQL e bancos de dados
* ⚙️ N8N e automação de workflows
* 🔀 Git e GitHub
* 🤖 Inteligência Artificial aplicada ao aprendizado

Mais do que simplesmente reunir informações, o projeto busca demonstrar um processo de **pesquisa, curadoria, experimentação, questionamento e consolidação do conhecimento**.

---

# 🎯 Contexto e Objetivos

## Contexto

Durante meus estudos na área de tecnologia, percebi que diversas ferramentas e conceitos estão diretamente relacionados.

Python pode ser utilizado para desenvolver aplicações e consumir APIs. APIs permitem a comunicação entre diferentes sistemas. SQL possibilita trabalhar com dados armazenados em bancos de dados. O N8N permite conectar sistemas e automatizar processos.

O objetivo do **Tech Brain** é justamente compreender essas relações de forma estruturada.

O **NotebookLM** foi utilizado como uma espécie de "cérebro" do projeto, centralizando as fontes de estudo e auxiliando na exploração dos conteúdos por meio de perguntas e prompts.

## Objetivo geral

Construir uma base de conhecimento organizada sobre tecnologias fundamentais para desenvolvimento, integração de sistemas, dados e automação.

## Objetivos específicos

* Compreender os fundamentos da linguagem Python;
* Entender o funcionamento de APIs e APIs REST;
* Aprender os principais conceitos de SQL;
* Compreender como sistemas podem se comunicar através de APIs;
* Entender conceitos fundamentais de automação com N8N;
* Compreender a função do Git e GitHub no desenvolvimento;
* Utilizar Inteligência Artificial como ferramenta de aprendizagem;
* Desenvolver técnicas de engenharia de prompts;
* Organizar e consolidar o conhecimento adquirido em um miniguia.

---

# 📚 Curadoria de Fontes

Para construir o conhecimento do Tech Brain, foram selecionadas fontes abertas e, prioritariamente, documentações oficiais.

A escolha das fontes levou em consideração:

* Autoridade da fonte;
* Qualidade e clareza do conteúdo;
* Atualidade das informações;
* Relação direta com os objetivos do projeto;
* Possibilidade de utilização como material de referência no NotebookLM.

## 🐍 Python

**Documentação oficial do Python**

https://docs.python.org/3/

Fonte utilizada para compreender conceitos fundamentais da linguagem, sintaxe, estruturas e recursos disponíveis.

---

## 🔗 APIs

**MDN Web Docs — HTTP**

https://developer.mozilla.org/en-US/docs/Web/HTTP

Material utilizado para compreender conceitos relacionados à comunicação HTTP, requisições, respostas, métodos e códigos de status.

---

## 🗄️ SQL

**PostgreSQL Documentation**

https://www.postgresql.org/docs/;


https://www.postgresql.org/about/

Fonte utilizada como referência para conceitos relacionados a bancos de dados relacionais e SQL.

---

## ⚙️ N8N

**Documentação oficial do N8N**

https://docs.n8n.io/

Fonte principal para compreender workflows, nodes, integrações, credenciais, webhooks e automações.

---

## 🔀 Git

**Git Documentation**

https://git-scm.com/doc

Fonte utilizada para compreender controle de versão e os principais conceitos e comandos do Git.

---

# 🧠 NotebookLM como ferramenta de aprendizagem

O NotebookLM foi utilizado como uma ferramenta de **aprendizagem ativa**, e não apenas como um mecanismo para obter respostas.

As fontes foram inseridas na ferramenta e utilizadas para realizar perguntas, comparar conceitos, solicitar explicações e identificar relações entre os diferentes assuntos.

Testes:

PERGUNTA1:

Estou desenvolvendo uma automação que precisa receber dados de uma API REST, tratar essas informações e armazená-las em um banco de dados SQL. Explique como eu poderia estruturar essa solução utilizando Python, APIs, SQL, Git e n8n. Mostre o papel de cada tecnologia, como elas se conectam e quais cuidados devo ter com autenticação, tratamento de erros e versionamento.

RESPOSTA1:

Para estruturar uma automação robusta que consome uma API REST, processa dados em Python, persiste informações em um banco SQL, utiliza o n8n como orquestrador e gerencia o código com Git, é fundamental definir bem a responsabilidade de cada camada1more_horiz.1. Papel de cada tecnologia na arquiteturaAPI REST: Atua como a fonte externa de dados56. A comunicação ocorre via protocolo HTTP (com métodos como GET, POST, PUT, DELETE), retornando dados padronizados em formato JSON1more_horiz.n8n: Funciona como o orquestrador do fluxo210. Ele agenda execuções (cron/timer) ou reage a gatilhos (webhooks), consome os endpoints HTTP, direciona os dados entre as etapas e aciona scripts ou bancos de dados11more_horiz.Python: Responsável pela transformação avançada e validação dos dados15more_horiz. Pode ser executado em nó de código (Code Node) dentro do próprio n8n ou via scripts/microserviços externos chamados pelo fluxo1415.SQL (Banco de Dados): Realiza a persistência estruturada e relacional318. Garante a integridade das informações armazenadas através de tabelas, chaves e restrições (constraints)1920.Git: Responsável pelo controle de versão e governança421. Armazena os scripts Python, arquivos de migração/queries SQL e os fluxos exportados em JSON do n8n422.2. Como as tecnologias se conectam no fluxo de dadosGatilho de Início (n8n): Um nó de agendamento (Schedule) no n8n dispara a automação em intervalos definidos (ex: diariamente)1223.Requisição HTTP (n8n $\rightarrow$ API REST): O n8n utiliza o nó HTTP Request para enviar a solicitação com os cabeçalhos de autenticação e parâmetros necessários1124.Recepção do JSON (API REST $\rightarrow$ n8n): A API valida a autorização e retorna o payload JSON com o status HTTP 200 OK9more_horiz.Tratamento de Dados (Python):O n8n passa a carga JSON para um nó de código em Python ou executa um script externo1415.O Python limpa campos indesejados, formata datas, converte tipos de dados e aplica regras de negócio15more_horiz.Gravação no Banco (n8n/Python $\rightarrow$ SQL): As instruções SQL (INSERT, UPDATE ou Upsert) persistem os dados validados nas tabelas correspondentes3more_horiz.Rastreabilidade (Git): Alterações nos scripts de tratamento, modificações nas tabelas SQL e versões dos workflows do n8n são commitadas no repositório422.3. Cuidados fundamentaisAutenticação e SegurançaGerenciamento de Credenciais: Nunca insira chaves de API, senhas ou tokens diretamente no código ou em arquivos públicos30more_horiz. Utilize as Credenciais nativas do n8n ou variáveis de ambiente (.env)33more_horiz.Uso de Headers: Envie tokens (como Bearer Token ou OAuth) dentro dos cabeçalhos das requisições HTTP para manter a comunicação segura36more_horiz.Proteger o Repositório: Adicione arquivos .env ou chaves privadas ao arquivo .gitignore para evitar vazamentos no Git/GitHub30more_horiz.Tratamento de Erros e ResiliênciaStatus Codes HTTP: Verifique os códigos de resposta da API2536. Erros do cliente (4xx, como 401 Unauthorized ou 404 Not Found) exigem correção na requisição25more_horiz. Erros do servidor (5xx) exigem mecânica de tentar novamente (retry)42.Blocos de Exceção em Python: Trate falhas de parsing ou dados ausentes usando blocos try/except (ValueError, KeyError, erros de conexão) para evitar a interrupção abrupta da execução43more_horiz.Tratamento no n8n: Configure caminhos de falha (Error Trigger ou sub-fluxos de erro) para alertar a equipe (ex: envio de e-mail/notificação) caso a API ou o banco fiquem indisponíveis4647.Versionamento e EvoluçãoVersionamento de Código (Git): Utilize branches (ex: main para produção, develop para desenvolvimento) para alterar regras de conversão em Python ou scripts SQL antes de promover para produção421.Versionamento de Workflows n8n: Exporte regularmente seus fluxos do n8n no formato JSON e salve-os na estrutura de pastas do seu repositório Git422.Versionamento de APIs: Atente-se às versões dos endpoints da API consumida (ex: /v1/, /v2/) para garantir compatibilidade quando o provedor atualizar a interface48.💡 Próximo passo sugerido: Se desejar, posso escrever um exemplo prático do script Python para parsing desse JSON ou montar a estrutura do comando SQL INSERT/UPDATE para a sua tabela.

PERGUNTA2:

Analise sua resposta anterior e faça uma verificação crítica baseada exclusivamente nas fontes deste notebook. Identifique quais afirmações estão diretamente fundamentadas nas fontes, quais são generalizações ou dependem da versão da ferramenta e quais informações precisam ser corrigidas ou complementadas. Não use conhecimento externo às fontes.

RESPOSTA2:

Uma análise crítica da resposta anterior confrontada estritamente com os materiais e documentações presentes neste notebook permite verificar o que está sustentado pelas fontes, o que representa generalização teórica e quais pontos requerem ajuste.1. Afirmações diretamente fundamentadas nas fontesAs seguintes definições e mecânicas descritas na resposta anterior estão totalmente alinhadas com o conteúdo dos cursos e documentações do notebook:Papel e Arquitetura do REST API e HTTP:A comunicação entre sistemas ocorre via protocolo HTTP, utilizando requisições e respostas1lock.Os verbos HTTP (GET, POST, PUT, DELETE) representam as operações de leitura, criação, atualização e remoção (CRUD) de recursos2more_horiz.O padrão de troca de dados padrão é o formato JSON6more_horiz.A arquitetura REST é sem estado (stateless), exigindo que cada requisição traga as informações necessárias1more_horiz.O versionamento de APIs pode ser realizado inserindo a versão diretamente na URI do endpoint (ex: /v1/, /v2/)1213.Orquestração e Fluxos no n8n:O n8n conecta aplicações por meio de um fluxo visual de nós (workflows)1415.A execução pode ser iniciada por gatilhos (triggers) variados, como agendamentos temporais (Schedule)1617, webhooks18, formulários19 ou disparos manuais20.Requisições HTTP arbitrárias são realizadas via nó HTTP Request21more_horiz, e há nós integrados para aplicações específicas2425.O n8n possui suporte a nó de código (Code Node) para execução de scripts de transformação2526.Fluxos criados no n8n podem ser baixados/exportados como arquivos no formato JSON27.Tratamento de Dados em Python:A linguagem permite estruturar e transformar coleções de dados utilizando listas, dicionários e métodos de manipulação de texto2829.O tratamento de falhas e exceções de execução é feito por blocos try/except30more_horiz.Modelagem e Persistência em SQL:O SQL é a linguagem padronizada para definição (DDL) e manipulação (DML) de bancos de dados relacionais33more_horiz.As tabelas garantem a integridade dos dados por meio de restrições (constraints) como Primary Key, Foreign Key, Not Null, Unique, Check e Default36more_horiz.A gravação e alteração de registros utilizam os comandos INSERT e UPDATE3442.Controle de Versão com Git e GitHub:O Git é um sistema distribuído de controle de versão que registra o histórico do projeto por meio de commits, branches e repositórios43more_horiz.O GitHub atua como hospedagem remota em nuvem, permitindo backup e trabalho colaborativo46.Autenticação e Erros:A autenticação HTTP utiliza cabeçalhos como Authorization (ex: Bearer Token) ou chaves de API21more_horiz.Códigos de status HTTP indicam o resultado do processamento: faixa 200 para sucesso, 401 para não autorizado, 4xx para erros do cliente e 5xx para erros internos do servidor6more_horiz.O n8n gerencia credenciais de acesso de forma centralizada e isolada24more_horiz.2. Generalizações e conceitos não detalhados nas fontesAlguns trechos da resposta anterior trouxeram termos ou práticas que, embora comuns no mercado, não possuem respaldo direto ou detalhado nas passagens deste notebook:Integração Automática n8n $\leftrightarrow$ Git: A resposta mencionou versionar workflows do n8n no Git. As fontes confirmam que é possível fazer o download manual do fluxo em formato JSON no n8n27 e que arquivos do projeto podem ser commitados no Git4546, mas não há menção nas fontes sobre sincronização automática nativa entre o n8n e um repositório Git.Comando "Upsert": Foi citada a operação de Upsert no banco SQL. As fontes abordam detalhadamente a inserção (INSERT) e a atualização (UPDATE)3442, mas o conceito ou comando específico de Upsert não é mencionado no material.Nomes Fixos de Branches (main / develop): O uso de ramificações (branches) é fundamentado4446, porém a convenção de nomes específicos como main ou develop não é abordada ou exigida nas fontes.Alertas do n8n via "Error Trigger": As fontes documentam a visualização de erros no painel de execuções (Executions) do n8n5153, mas o nó específico denominado Error Trigger para direcionamento automático de notificações de erro não aparece nas transcrições do curso de n8n.Microserviços Externos em Python: A resposta citou a execução de Python via microserviços externos. As fontes tratam do uso de scripts Python locais/módulos5455 ou da utilização do nó de código dentro do próprio n8n2526, sem detalhar arquiteturas de microserviços em nuvem.3. Ajustes e complementações com base estrita nas fontesLinguagem Padrão no Nó de Código do n8n: O nó Code do n8n executa nativamente JavaScript ou Python2526. Nas aulas práticas de n8n contidas no notebook, as transformações e manipulações de itens JSON do fluxo são demonstradas majoritariamente em JavaScript2656.Estrutura dos Dados no n8n: A passagem de dados entre os nós do n8n ocorre em estruturas formatadas em objetos/arrays JSON957. Para extrair e mapear campos para comandos SQL ou chamadas de API, utiliza-se a sintaxe de expressões ou nós auxiliares de edição de campos (Edit/Set Fields)57more_horiz.Proteção de Segredos: O uso de variáveis de ambiente (.env) é abordado em contextos de código60. No Git, a instrução para desconsiderar arquivos sensíveis (como .env) é configurada no arquivo .gitignore6162.O mapeamento arquitetural entre API REST, n8n, Python, SQL e Git permanece conceitualmente correto, porém a execução prática deve se atentar ao fato de que o versionamento do n8n depende da exportação dos arquivos JSON para o repositório Git2745.Caso queira prosseguir, posso estruturar o script de criação da tabela SQL com as devidas restrições (constraints)3336 ou exemplificar a manipulação do payload em Python2629.

PERGUNTA3:

Uma API está retornando erro 401 ao tentar fazer uma requisição pelo n8n. Usando exclusivamente as fontes deste notebook, faça um diagnóstico passo a passo. Explique o que significa o erro 401, quais pontos devo verificar na configuração da requisição, como verificar autenticação e headers, e quais informações eu deveria coletar antes de tentar corrigir o problema. Não invente soluções que não estejam fundamentadas nas fontes.

RESPOSTA3:

Com base estritamente nos materiais e documentações presentes neste notebook, aqui está o diagnóstico passo a passo para identificar e resolver o erro **401** em uma requisição feita pelo **n8n**.

---

### Step 1: Compreender o significado do erro HTTP 401

* **O que significa**: O código de status **401** indica **"Não autorizado"** (*Unauthorized*)[1].
* **Causa principal**: Ele ocorre quando o servidor da API recebe a requisição, mas a recusa porque as credenciais, a chave de API ou as informações de autorização estão ausentes, incorretas ou inválidas[1][2].
* **Classificação HTTP**: Erros na faixa de código **400** sinalizam que houve uma falha do lado do cliente ao montar a requisição (como falta de permissão ou formato incorreto)[3][4].

---

### Step 2: Pontos a verificar na configuração da requisição no n8n

1. **Atribuição da Credencial no Nó**:
  * Caso esteja utilizando um nó de aplicação específica ou o nó *HTTP Request*, verifique se uma credencial foi criada e associada ao nó[5].
  * Se o nó tentar executar a chamada sem uma credencial configurada ou com uma chave em branco, o servidor retornará 401[1][2].
2. **Envio e Formatação dos Cabeçalhos (** **Headers** **)**:
  * Caso a requisição seja feita via nó *HTTP Request* e configurada manualmente para enviar *headers*, confirme se a chave `Authorization` foi incluída[2][5].
  * Verifique se o formato exigido pela API foi respeitado (por exemplo, preceder o token com a palavra `Bearer `, gerando o valor `Bearer'<token>) [2][5].
  * Certifique-se de que outros cabeçalhos obrigatórios para envio de dados, como `Content-Type: application/json`, foram preenchidos no nó [5].

3.**Integridade da Chave / Token**:
* Confirme se a chave de API ou token de acesso (*Access Token*) não foi digitada com espaços extras ou sem as aspas/delimitadores necessários[2].
* Se for uma autenticação via token temporário ou OAuth, valide se o token não expirou[8][9].

### Step 3: Como verificar a autenticação e os headers

1. **Verificação na área de Credenciais do n8n**:
  * Acesse o menu de credenciais do n8n (ou as configurações de credencial do próprio nó) e valide se o token ou a chave de API (*API Key*) cadastrada está atualizada[6].
2. **Verificação da Transmissão por Cabeçalho**:
  * Lembre-se de que requisições HTTP REST não mantêm estado (*stateless*); portanto, cada requisição individual precisa enviar as informações de login/autenticação nos cabeçalhos[4][11].
  * No nó *HTTP Request*, abra as opções de envio de *Headers* e inspecione se a relação chave-valor para autorização (`Authorization`) está ativada e devidamente preenchida[2][5].
3. **Confronto com a Documentação da API**:
  * Acesse a seção de autorização da documentação do serviço externo[10][12].
  * Verifique qual tipo de autenticação a API exige (API Key, Bearer Token ou OAuth) e qual o nome exato do parâmetro ou cabeçalho esperado pelo servidor[9].

### Step 4: Informações a coletar antes de tentar corrigir o problema

Antes de alterar a automação, colete os seguintes dados para isolar a causa:

1. **Documentação de Autorização da API**: O trecho da documentação oficial que define o endpoint, os parâmetros obrigatórios e o método de autenticação exigido[10][12].
2. **Token ou Chave de API Válida**: A chave gerada na área de desenvolvedor ou integrações da aplicação externa[2][10].
3. **Payload e Mensagem de Resposta de Erro**: O retorno em formato JSON exibido no painel de execução ou na saída do nó no n8n[1]. Em muitas APIs, o corpo da resposta 401 descreve o motivo exato (ex: *"token expired"*, *"invalid key"* ou *"missing credentials"*)[1][13].
4. **Lista de Headers Enviados na Chamada**: A checagem visual de todos os cabeçalhos (`Authorization`, `Content-Type`, etc.) que foram configurados para sair do nó do n8n[2][5].

🔍 **Sugestão de próximo passo**: Se você tiver a documentação da API em mãos ou a mensagem JSON que o n8n recebeu no erro, posso ajudar a formatar o cabeçalho `Authorization` ou indicar exatamente como preencher a credencial no nó.

PERGUNTA4:

Explique para uma pessoa que está começando em tecnologia o que acontece desde o momento em que o n8n envia uma requisição para uma API REST até receber a resposta. Use uma analogia simples e depois explique tecnicamente o mesmo processo, relacionando HTTP, método GET, URL, headers, autenticação, JSON, código de status e n8n. Baseie-se exclusivamente nas fontes deste notebook e indique quando uma informação não estiver disponível nas fontes.

RESPOSTA4:

Entender como o **n8n** se comunica com uma **API REST** fica muito mais simples quando dividimos o processo entre uma metáfora do dia a dia e os conceitos técnicos reais.

---

### 1\. A analogia do restaurante 🍽️

Pense no processo como fazer um pedido em um restaurante:

* **O Cliente na mesa (n8n)**: Você está sentado e quer consumir algo. Você não entra na cozinha para preparar a comida; em vez disso, você monta o seu pedido[1][2].
* **O Garçom (HTTP)**: É o meio de transporte padronizado que leva a mensagem da sua mesa até a cozinha e traz a resposta de volta[3].
* **O Cardápio e o Endereço (URL e Método GET)**: O endereço do restaurante e o item específico do cardápio que você aponta é a **URL**[4][5]. Quando você apenas pede para *ver* ou *receber* um prato sem alterar a receita, você está fazendo um pedido do tipo **GET**[6][7].
* **As Observações do Pedido e o Cartão de Membro (Headers e Autenticação)**: Junto com o pedido, você entrega o seu cartão de fidelidade ou documento com foto para provar que tem permissão para pedir daquele cardápio[8][9]. Essas informações de identificação e preferências são os **Headers**[9][10].
* **A Cozinha e o Chef (Servidor da API REST)**: A cozinha recebe a comanda, confere seu documento, busca os ingredientes e prepara o prato[11][12].
* **O Prato Pronto e a Nota de Entrada (JSON e Código de Status)**: O garçom retorna trazendo o prato arrumado em uma marmita padronizada (**JSON**) e um aviso verbal (**Código de Status**), por exemplo: *"Aqui está o seu prato!"* (Sucesso / 200 OK) ou *"Você não tem permissão para pedir esse item"* (Erro / 401 Unauthorized)[12].

---

### 2\. O processo técnico passo a passo

Quando o nó do **n8n** é executado, ocorre a seguinte sequência de eventos no sistema:

#### Passo 1: O n8n inicia a requisição HTTP

O **n8n** atua como o cliente (*agente-usuário*) que inicia ativamente a comunicação enviando uma solicitação. Ele utiliza um protocolo de camada de aplicação chamado **HTTP** (*Hypertext Transfer Protocol*), que estabelece as regras universais de envio e recebimento de mensagens na Web[3].

#### Passo 2: Definição da URL e do Método GET

No n8n (seja em um nó específico de aplicação ou no nó *HTTP Request*), é configurada a **URL** (*Uniform Resource Locator*), que é o endereço digital exclusivo do recurso que se deseja acessar no servidor[4]. O n8n define o método HTTP como **GET**, informando ao servidor que a intenção é estritamente consultar e ler dados existentes, sem realizar modificações no sistema[6].

#### Passo 3: Envio de Headers e Autenticação

Junto com o método e a URL, o n8n empacota os **Headers** (cabeçalhos), que são pares de chave-valor contendo metadados da requisição[10]. Entre esses cabeçalhos, inclui-se a **autenticação** (como uma chave de API ou um *Bearer Token* no parâmetro `Authorization`)[8]. Como o protocolo HTTP é *stateless* (não guarda estado nem memória de acessos anteriores), o n8n precisa enviar essas credenciais de autorização em absolutamente cada requisição realizada[8].

#### Passo 4: Processamento pela API REST no servidor

A **API REST** (*Representational State Transfer*) hospedada no servidor remoto recebe o pacote HTTP[11]. O servidor lê os cabeçalhos, valida se a chave de autenticação é legítima e tem permissão de acesso, busca a informação requisitada no banco de dados e prepara a resposta[9].

#### Passo 5: Retorno com Código de Status e corpo JSON

O servidor devolve uma resposta HTTP dividida em duas partes essenciais:

1. **Código de Status (Status Code)**: Um código numérico que informa o resultado imediato do processamento[8]. Se o acesso for permitido e os dados encontrados, retorna **200 OK**[12]. Se a chave estiver incorreta ou ausente, retorna **401 Unauthorized**[12][14].
2. **Corpo da Resposta (Body) em JSON**: Se o status for de sucesso, os dados retornam formatados em **JSON** (*JavaScript Object Notation*)[14]. O JSON organiza as informações em uma estrutura legível de chaves e valores (ou listas de objetos), que pode ser convertida diretamente por qualquer linguagem ou sistema[19][20].

#### Passo 6: Leitura e fluxo no n8n

O n8n recebe a resposta HTTP, interpreta o código de status e converte o *payload* JSON em objetos estruturados no painel visual[21]. A partir desse momento, os dados ficam disponíveis para serem manipulados por novos nós do *workflow* (como enviá-los para um banco de dados SQL ou tratá-los via Python)[2].

---

### 3\. O que não está coberto nas fontes deste notebook

Para manter o rigor com os materiais disponíveis:

* **Infraestrutura física de rede e handshake TCP/IP**: As fontes explicam que o HTTP roda sobre o protocolo TCP e que a arquitetura Web abstrai as camadas inferiores (roteadores, modems e pacotes IP)[3], mas **não detalham o processo baixo nível de resolução de DNS ou o handshake de três vias do TCP** que ocorre antes de a mensagem HTTP ser transmitida.

---

🔧 **Sugestão de próximo passo**: Quer que eu mostre como estruturar a extração desses campos JSON recebidos no n8n para montar o comando SQL `INSERT` correspondente?

Essa abordagem permitiu transformar informações isoladas em uma estrutura de conhecimento mais conectada.

---

# 💬 Engenharia de Prompts

Uma das etapas do projeto foi experimentar diferentes formas de fazer perguntas à Inteligência Artificial.

O objetivo não era apenas obter uma resposta, mas aprender a formular perguntas que produzissem respostas mais úteis, contextualizadas e relacionadas às fontes selecionadas.


### Objetivo

Compreender que as tecnologias não funcionam necessariamente de forma isolada, podendo fazer parte de uma mesma solução.

---

# 🩹 Cicatrizes e Troubleshooting

Durante o processo de aprendizagem, algumas respostas iniciais não apresentaram o nível de profundidade desejado.

Um dos principais aprendizados foi perceber que **a qualidade da pergunta influencia diretamente a qualidade da resposta**.

### Problema

Perguntas muito genéricas produziam respostas amplas e pouco direcionadas.

### Solução

Adicionar contexto, objetivo, nível de conhecimento, exemplos e restrições à pergunta.

Por exemplo:

```
Pergunta genérica:

"O que é API?"

↓

Pergunta contextualizada:

"Explique API REST para uma pessoa que já conhece
Python básico, mas ainda não entende como sistemas
diferentes se comunicam. Mostre um exemplo de uma
requisição GET feita em Python."
```

### Principal aprendizado

A engenharia de prompts não consiste apenas em escrever perguntas longas.

Um bom prompt deve fornecer **contexto e objetivo claros**, direcionando a IA para o tipo de resposta necessário.

---

# 📖 Miniguia de Estudos

# 🐍 1. Python

Python é uma linguagem de programação de alto nível, conhecida pela sintaxe relativamente simples e por sua ampla utilização em desenvolvimento, automação, análise de dados e Inteligência Artificial.

### Conceitos estudados

* Variáveis
* Tipos de dados
* Condicionais
* Estruturas de repetição
* Funções
* Listas e dicionários
* Módulos
* Bibliotecas
* Tratamento de exceções
* Consumo de APIs



# 🔗 2. APIs

API significa **Application Programming Interface**.

Uma API permite que diferentes sistemas se comuniquem seguindo regras previamente definidas.

Em uma API REST, é comum utilizar métodos HTTP como:

| Método | Função                 |
| ------ | ---------------------- |
| GET    | Consultar dados        |
| POST   | Criar dados            |
| PUT    | Atualizar dados        |
| PATCH  | Atualizar parcialmente |
| DELETE | Excluir dados          |

### Conceitos importantes

**Endpoint:** endereço específico de um recurso da API.

**Request:** requisição enviada pelo cliente.

**Response:** resposta enviada pelo servidor.

**Status Code:** código que indica o resultado da requisição.



# 🗄️ 3. SQL

SQL significa **Structured Query Language**.

É utilizada para consultar e manipular dados em bancos de dados relacionais.

### Principais comandos

```sql
SELECT
INSERT
UPDATE
DELETE
```

### Conceitos estudados

* Tabelas
* Registros
* Colunas
* Chaves primárias
* Chaves estrangeiras
* SELECT
* WHERE
* ORDER BY
* GROUP BY
* JOIN
* INSERT
* UPDATE
* DELETE

---

# ⚙️ 4. N8N

O **N8N** é uma plataforma de automação de workflows que permite conectar diferentes sistemas e serviços.

Um workflow pode ser representado de maneira simplificada:

```text
Gatilho
   ↓
Receber informação
   ↓
Processar dados
   ↓
Consultar API
   ↓
Consultar banco de dados
   ↓
Executar ação
```

### Conceitos importantes

* Workflow
* Node
* Trigger
* Webhook
* HTTP Request
* Credentials
* Expressions
* Automação
* Integração

O N8N pode funcionar como uma camada de integração entre diferentes sistemas.

---

# 🔀 5. Git e GitHub

Git é um sistema de controle de versão utilizado para acompanhar alterações em projetos.

O GitHub é uma plataforma que permite hospedar e compartilhar repositórios Git.

### Comandos fundamentais

```bash
git init
git add .
git commit -m "mensagem"
git status
git log
git push
git pull
```

### Conceitos

* Repositório
* Commit
* Branch
* Merge
* Clone
* Push
* Pull
* GitHub

O controle de versão permite acompanhar a evolução do projeto e manter um histórico das alterações.

---

# 🔗 Como as tecnologias se conectam?

Uma das principais conclusões do Tech Brain é que essas tecnologias podem fazer parte de um mesmo fluxo.

Um exemplo:

```text
                ┌─────────────┐
                │    n8n      │
                │ Automação   │
                └──────┬──────┘
                       │
                       ▼
                ┌─────────────┐
                │     API     │
                │ Comunicação │
                └──────┬──────┘
                       │
                       ▼
                ┌─────────────┐
                │   Python    │
                │ Processamento│
                └──────┬──────┘
                       │
                       ▼
                ┌─────────────┐
                │     SQL     │
                │    Dados    │
                └─────────────┘
```

Nesse cenário:

* **N8N** pode orquestrar o workflow;
* **API** pode permitir a comunicação entre sistemas;
* **Python** pode realizar processamento ou lógica específica;
* **SQL** pode armazenar e consultar informações;
* **Git/GitHub** pode controlar a versão do código e documentar o projeto.

---

# 📖 Glossário

| Termo      | Definição                                             |
| ---------- | ----------------------------------------------------- |
| API        | Interface que permite comunicação entre sistemas      |
| REST       | Arquitetura utilizada para construção de APIs         |
| Endpoint   | URL que representa um recurso de uma API              |
| HTTP       | Protocolo utilizado na comunicação web                |
| JSON       | Formato estruturado para troca de dados               |
| Request    | Requisição enviada a um servidor                      |
| Response   | Resposta recebida do servidor                         |
| CRUD       | Create, Read, Update e Delete                         |
| SQL        | Linguagem para manipulação de bancos relacionais      |
| Database   | Banco de dados                                        |
| Query      | Consulta realizada em um banco                        |
| Webhook    | Mecanismo para receber eventos através de requisições |
| Workflow   | Sequência de etapas de um processo automatizado       |
| Node       | Unidade de execução dentro de um workflow n8n         |
| Git        | Sistema de controle de versão                         |
| Repository | Local onde o código e seu histórico são armazenados   |
| Commit     | Registro de uma alteração no Git                      |
| Branch     | Linha independente de desenvolvimento                 |

---

# ♻️ Prompts Reutilizáveis

Os prompts abaixo podem ser utilizados posteriormente para revisão dos conteúdos.

### 📚 Explicação de conceito

> Explique [CONCEITO] de forma didática, começando pelo nível básico e avançando gradualmente. Apresente um exemplo prático e explique os principais conceitos relacionados.

### 🔍 Comparação

> Compare [CONCEITO A] e [CONCEITO B]. Explique as diferenças, semelhanças, vantagens, limitações e quando cada um pode ser utilizado.

### 🧩 Resolução de problema

> Estou enfrentando o seguinte problema: [DESCREVA O PROBLEMA]. Analise possíveis causas, apresente uma solução passo a passo e explique o motivo de cada etapa.

### 🧠 Revisão

> Faça uma revisão dos principais conceitos de [TEMA]. Organize a resposta em tópicos, destaque os pontos mais importantes e apresente exemplos práticos.

### 🔗 Conexão entre tecnologias

> Explique como [TECNOLOGIA A], [TECNOLOGIA B] e [TECNOLOGIA C] podem trabalhar juntas em um projeto real. Apresente um fluxo passo a passo.

### 🧪 Aprendizagem ativa

> Faça 5 perguntas sobre [TEMA], começando por conceitos básicos e aumentando gradualmente a dificuldade. Não apresente as respostas imediatamente. Depois que eu responder, avalie minhas respostas e explique meus erros.

---

# 💡 Principais aprendizados

Ao longo do desenvolvimento do Tech Brain, alguns aprendizados se destacaram:

1. **Aprender tecnologia não significa apenas memorizar comandos.**
2. **Relacionar conceitos diferentes facilita a compreensão de sistemas completos.**
3. **Fontes confiáveis são fundamentais para reduzir informações incorretas.**
4. **Perguntas bem estruturadas produzem respostas mais úteis.**
5. **A IA pode atuar como ferramenta de aprendizagem, mas o pensamento crítico continua sendo essencial.**
6. **Documentar erros e tentativas também faz parte do processo de aprendizagem.**
7. **Tecnologias como Python, APIs, SQL e n8n podem ser utilizadas de forma integrada.**

---

# 🚀 Próximos passos

O Tech Brain continuará evoluindo conforme novos conhecimentos forem adquiridos.

Possíveis próximos temas:

* Docker
* Linux
* JavaScript
* FastAPI
* Automação com Python
* Integração de APIs
* Bancos de dados relacionais
* Webhooks
* LLMs e Inteligência Artificial
* RPA
* Arquitetura de sistemas
* Projetos práticos utilizando n8n

---

# 👩‍💻 Autora

**Natália de Melo Dias**

Projeto desenvolvido como parte de um desafio prático de aprendizagem da **DIO**, utilizando Inteligência Artificial, curadoria de fontes e organização do conhecimento.

---

## 📌 Status do projeto

🟡 **Em desenvolvimento**

O conhecimento será atualizado conforme novos estudos, experimentos e projetos forem realizados.

---

⭐ **Se este projeto foi útil para você, considere deixar uma estrela no repositório!**

