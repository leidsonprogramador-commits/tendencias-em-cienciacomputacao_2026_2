# Sistema NotaÁgil — Lançamento de Nota Fiscal

## Visão Geral do Sistema

O **NotaÁgil** foi concebido para otimizar e automatizar o processo de entrada de notas fiscais, eliminando tarefas manuais e repetitivas. O sistema permite o lançamento em segundos a partir de Chave de Acesso, XML, PDF ou Foto, realizando o cadastro automático de fornecedores e produtos com validações e verificações inteligentes.

---

## 1. Módulos e Telas do Sistema

O sistema conta com um menu lateral fixo para navegação entre os principais módulos:

* **Cadastro de Nota** (Lançamento e captura)
* **Fornecedores** (Consulta e gestão cadastral)
* **Produtos** (Catálogo de itens vinculados aos fornecedores)
* **Usuários** (Administração de contas e permissões)

---

## 2. Autenticação e Controle de Acesso

### 2.1. Tela de Login

* Interface inicial do sistema NotaÁgil com slogan *"Nota lançada em segundos. Fornecedor e produtos cadastrados."*
* Formulário de autenticação para validação de acesso.

### 2.2. Perfil Administrador

* **Acesso Inicial:** Reservado ao administrador do sistema no primeiro acesso.
* **Autonomia do Administrador:**
  * Registro de novos usuários no painel de **Usuários**.
  * Definição granular de acessos e permissões por campo/funcionalidade.
  * Acesso total às configurações globais da aplicação.

---

## 3. Lançamento e Cadastro de Nota Fiscal

### 3.1. Formas de Entrada

O sistema aceita quatro formas de entrada de dados:

1. Chave de acesso de NFe
2. Importação de arquivo XML
3. Upload de arquivo PDF
4. Captura ou upload de foto/imagem

---

### 3.2. Estrutura da Tela de Cadastro de Nota

A tela de lançamento é dividida em blocos bem definidos:

#### A) Seção Fornecedor
Captura e cadastra automaticamente os dados do fornecedor:
* **Razão Social**
* **Nome Fantasia**
* **CNPJ**
* **CEP**
* **Telefone**
* **Endereço Completo**
* *Ação:* Botão para confirmação ou edição manual dos dados.

#### B) Seção Nota
Contém as informações gerais do documento fiscal:
* **Chave de Acesso** (44 dígitos)
* **Número da Nota**
* **Série**
* **Data de Emissão**
* **Valor Total da Nota**

#### C) Seção Produtos
Listagem dos itens extraídos do documento fiscal:
* **Colunas:** Código, Descrição do Produto, NCM, UND (Unidade de Medida), QTD (Quantidade), V. UN. (Valor Unitário), Total e Alertas.
* **Ações de Controle:**
  * Botões de ação rápida: `Já cadastrado`, `Novo` e `Em alerta`.
  * Botão de confirmação para salvar edições feitas no formulário.
  * Botão final: `Confirmar e lançar nota`.

---

## 4. Regras de Negócio e Verificações Automáticas

### 4.1. Verificação de Duplicidade e Cadastro de Itens

* Ao importar os dados, o sistema cruza os produtos obtidos com o banco de dados do fornecedor.
* Sinalização visual clara separando os itens que **já possuem cadastro** daqueles que **serão adicionados pela primeira vez**.

### 4.2. Verificação de Informações Cruzadas

* O sistema verifica se as informações de um fornecedor ou produto coincidem ou conflitam com dados de outros fornecedores.
* **Alertas do Sistema:** Criação automática de um alerta na interface em caso de divergência, permitindo que o usuário edite e corrija a inconsistência antes do lançamento final.

---

## 5. Módulos de Consulta e Gestão

### 5.1. Tela de Fornecedores
* Módulo para busca e listagem detalhada dos fornecedores cadastrados, com histórico de notas e contatos.

### 5.2. Tela de Produtos
* Tabela de produtos com filtros por fornecedor e campo de pesquisa por descrição, código ou NCM.
* Exibição do código, descrição, NCM, unidade de medida, valor unitário e fornecedor associado.
* Botão de edição rápida (`✏️`) para cada item da lista.

### 5.3. Tela de Usuários
* Painel administrativo para cadastro, edição, bloqueio de contas e configuração de níveis de permissão.