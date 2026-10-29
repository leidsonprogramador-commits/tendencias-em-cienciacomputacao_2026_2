# Sistema de Lançamento de Nota Fiscal

## Visão Geral do Sistema

O **Sistema de Lançamento de Nota Fiscal** foi concebido para suprir deficiências operacionais encontradas em soluções convencionais de mercado, proporcionando aos usuários um processo de entrada de dados mais rápido, prático e automatizado.

---

## 1. Controle de Acesso e Autenticação

### 1.1. Tela de Login
* Interface inicial para validação das credenciais de acesso de cada usuário.

### 1.2. Perfil Administrador
* **Acesso Inicial:** O primeiro login do sistema é reservado ao Administrador do Sistema.
* **Autonomia e Permissões:**
  * Gestão e registro de novos usuários.
  * Configuração granular de permissões e controle de acesso a campos específicos.
  * Acesso total e ilimitado a todas as funcionalidades do sistema.

---

## 2. Entrada de Dados e Captura da Nota Fiscal

### 2.1. Métodos de Lançamento
O sistema permite o processamento e a captura de notas fiscais através das seguintes modalidades:
* Chave de acesso da NFe
* Importação de arquivo XML
* Importação de arquivo PDF
* Captura e processamento por foto/imagem

### 2.2. Extração e Tratamento de Informações

#### 2.2.1. Cadastro Automático do Fornecedor
Ao ler a nota fiscal, o sistema extrai e cadastra automaticamente os dados do fornecedor:
* Razão Social
* Nome Fantasia *(se houver)*
* CNPJ
* CEP e Endereço
* Telefone de Contato

#### 2.2.2. Cadastro Automático dos Produtos
Extração e vinculação automática dos itens constantes na nota fiscal:
* Código do Produto
* Descrição do Produto
* NCM (*Nomenclatura Comum do Mercosul*)
* Unidade de Medida (UND)
* Quantidade (QTD)
* Valor Unitário (V. UN.)

#### 2.2.3. Edição e Confirmação de Dados
* Todas as informações obtidas automaticamente podem ser revisadas e editadas pelo usuário.
* Interface com botão explícito de confirmação para salvar as alterações.

---

## 3. Regras de Negócio e Verificações Automáticas

### 3.1. Checagem de Duplicidade e Cadastro Existente
* Durante o lançamento, o sistema compara os dados capturados com o banco de dados.
* Indicação clara dos produtos já existentes e daqueles que serão cadastrados como novos no banco do fornecedor.

### 3.2. Validação Cruzada de Informações
* **Alertas de Consistência:** Identificação automatizada de divergências ou duplicidades de dados entre fornecedores distintos.
* Exibição de alertas na tela para que o operador possa analisar e corrigir eventuais inconsitências.

---

## 4. Estrutura da Interface do Usuário

O sistema conta com um menu principal estruturado com as seguintes opções de navegação:
* **Cadastro de Nota Fiscal:** Módulo para inclusão e processamento de novas notas.
* **Visualização de Fornecedores:** Consulta e gestão dos dados cadastrais de fornecedores.
* **Visualização de Produtos:** Consulta e gestão do catálogo de itens e seus históricos.
* **Administração de Usuários:** Gestão de acessos, perfis e permissões pelo administrador.