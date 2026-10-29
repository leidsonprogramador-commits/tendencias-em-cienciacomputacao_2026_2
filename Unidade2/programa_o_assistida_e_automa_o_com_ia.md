# Programação Assistida e Automação com IA

## Identificação

* **Nome:** Leidson Arthur Santana Almeida

* **Data:** 17/09/2026

* **Disciplina:** Tendências em Ciência da Computação

* **Unidade:** II — Programação Assistida

* **Professora:** Kadidja Valéria

* **Ferramenta de IA utilizada:** ChatGPT

* **Atividade:** Opção A — Organização de Arquivos

## 1. Problema

Quero automatizar a organização de arquivos de uma pasta. O programa deverá identificar os arquivos existentes e organizá-los automaticamente em pastas de acordo com suas extensões.

**Exemplo inicial:**

```
trabalhos/
├── documento.pdf
├── imagem.jpg
├── foto.png
├── texto.txt
└── planilha.xlsx

```

**Após a organização:**

```
trabalhos/
├── pdf/
│   └── documento.pdf
├── jpg/
│   └── imagem.jpg
├── png/
│   └── foto.png
├── txt/
│   └── texto.txt
└── xlsx/
    └── planilha.xlsx

```

## 2. Entrada

O programa receberá como entrada o caminho de uma pasta contendo arquivos de diferentes extensões, como:

* `.pdf`

* `.jpg`

* `.png`

* `.txt`

* `.docx`

* `.xlsx`

## 3. Processamento

O programa deverá:

1. Acessar a pasta informada.

2. Identificar os arquivos existentes.

3. Verificar a extensão de cada arquivo.

4. Criar uma pasta para cada extensão encontrada, caso ela ainda não exista.

5. Mover cada arquivo para a pasta correspondente à sua extensão.

6. Evitar sobrescrever arquivos que já existam.

7. Informar ao usuário quais arquivos foram organizados.

## 4. Saída esperada

Como resultado, espero que os arquivos sejam organizados automaticamente em pastas de acordo com suas extensões.

**Exemplo:**

```
trabalhos/
├── pdf/
│   ├── trabalho1.pdf
│   └── trabalho2.pdf
├── jpg/
│   └── imagem.jpg
├── png/
│   └── foto.png
├── txt/
│   └── anotacao.txt
└── xlsx/
    └── planilha.xlsx

```

## 5. Prompt utilizado

```
PAPEL:
Atue como um desenvolvedor Python, auxiliando um estudante iniciante de Ciência da Computação.

CONTEXTO:
Estou realizando uma atividade acadêmica sobre Programação Assistida por IA e Automação. Preciso desenvolver um programa simples para automatizar a organização de arquivos em uma pasta.

PROBLEMA:
Preciso organizar automaticamente os arquivos existentes em uma pasta de acordo com suas extensões. Por exemplo, arquivos .pdf devem ficar em uma pasta pdf, arquivos .jpg em uma pasta jpg, arquivos .txt em uma pasta txt e assim por diante.

ENTRADA:
O programa deverá receber o caminho de uma pasta que contenha arquivos de diferentes extensões.

SAÍDA ESPERADA:
O programa deverá identificar as extensões dos arquivos, criar as pastas correspondentes quando necessário e organizar os arquivos em suas respectivas pastas. Ao final, deverá informar ao usuário quais arquivos foram organizados.

LINGUAGEM:
Utilize Python.

RESTRIÇÕES:
- Utilizar somente bibliotecas padrão do Python.
- Não excluir arquivos.
- Não modificar o conteúdo dos arquivos.
- Não sobrescrever arquivos existentes.
- Tratar arquivos que não possuam extensão.
- Informar possíveis erros durante a execução.
- O código deve ser simples e adequado para um estudante iniciante.
- Explicar o funcionamento do código antes de apresentar a solução completa.

CRITÉRIOS DE QUALIDADE:
- Código organizado e legível.
- Nomes de variáveis e funções claros.
- Tratamento básico de erros.
- Código dividido em funções quando necessário.
- Segurança para evitar perda ou sobrescrita de arquivos.
- Facilidade para compreender e explicar cada parte do programa.

CASOS DE TESTE:

Teste 1 — Caso normal:
Uma pasta contendo arquivos .pdf, .jpg, .txt e .xlsx.
Resultado esperado: cada arquivo deve ser colocado em uma pasta correspondente à sua extensão.

Teste 2 — Caso limite:
Uma pasta vazia ou contendo apenas um arquivo.
Resultado esperado: o programa deve executar sem apresentar erro inesperado e informar que não há arquivos para organizar ou organizar o único arquivo encontrado.

Teste 3 — Caso de erro:
Informar um caminho de pasta que não existe.
Resultado esperado: o programa deve informar que a pasta não foi encontrada, sem encerrar de maneira inesperada.

FORMATO DA RESPOSTA:
1. Explique a estratégia utilizada.
2. Explique os principais conceitos de Python utilizados.
3. Apresente o código completo.
4. Explique as principais funções do código.
5. Apresente exemplos de execução.
6. Explique como os três casos de teste podem ser realizados.

```

## 6. Código inicial

```python
import os
import shutil


def organizar_arquivos(caminho_pasta):
    # Teste 3: Verifica se o caminho existe e é um diretório
    if not os.path.isdir(caminho_pasta):
        print(
            f"Erro: O caminho '{caminho_pasta}' não foi encontrado ou não é uma pasta válida."
        )
        return

    try:
        # Lista todos os itens do diretório
        todos_itens = os.listdir(caminho_pasta)
    except Exception as e:
        print(f"Erro ao acessar a pasta: {e}")
        return

    # Filtra apenas os arquivos (ignora pastas já existentes)
    arquivos = [
        item
        for item in todos_itens
        if os.path.isfile(os.path.join(caminho_pasta, item))
    ]

    # Teste 2: Verifica se a pasta está vazia de arquivos
    if not arquivos:
        print("A pasta está vazia ou não contém arquivos para organizar.")
        return

    arquivos_organizados = 0

    print("\nIniciando a organização dos arquivos...\n")

    for arquivo in arquivos:
        caminho_original = os.path.join(caminho_pasta, arquivo)

        # Trata arquivos sem extensão
        nome_base, extensao = os.path.splitext(arquivo)

        if not extensao:
            nome_pasta_destino = "sem_extensao"
        else:
            nome_pasta_destino = extensao[1:].lower()

        # Define o caminho da nova subpasta
        pasta_destino = os.path.join(caminho_pasta, nome_pasta_destino)

        try:
            # Cria a pasta se ela não existir
            if not os.path.exists(pasta_destino):
                os.makedirs(pasta_destino)

            caminho_final = os.path.join(pasta_destino, arquivo)

            # Não sobrescreve arquivos existentes
            if os.path.exists(caminho_final):
                print(
                    f"[AVISO] O arquivo '{arquivo}' já existe "
                    f"na pasta '{nome_pasta_destino}'. Não foi movido."
                )
                continue

            # Move o arquivo
            shutil.move(caminho_original, caminho_final)
            print(f"-> Mover: '{arquivo}' para '{nome_pasta_destino}/'")
            arquivos_organizados += 1

        except Exception as e:
            print(f"[ERRO] Falha ao processar o arquivo '{arquivo}': {e}")

    print(
        f"\nProcesso concluído! Total de arquivos organizados "
        f"com sucesso: {arquivos_organizados}"
    )


# Bloco principal para execução do programa
if __name__ == "__main__":
    print("=== ASSISTENTE DE ORGANIZAÇÃO DE ARQUIVOS ===")
    caminho_usuario = input("Digite o caminho completo da pasta: ").strip()
    organizar_arquivos(caminho_usuario)
```

## 7. Análise crítica da primeira versão

### 7.1 Eu compreendo o código?

Sim. O programa utiliza duas bibliotecas:

* `os`: trabalha com caminhos, pastas e arquivos.

* `shutil`: permite mover os arquivos.

A função principal é `organizar_arquivos(caminho_pasta)`, que recebe o caminho da pasta a ser organizada.

### 7.2 O código atende ao problema?

Sim. O programa:

* verifica se a pasta existe;

* identifica os arquivos;

* verifica a extensão;

* cria pastas de acordo com as extensões;

* move os arquivos;

* evita sobrescrever arquivos existentes;

* trata arquivos sem extensão;

* apresenta mensagens durante a execução.

### 7.3 Existem bibliotecas que eu não conheço?

As bibliotecas utilizadas (`os` e `shutil`) fazem parte da biblioteca padrão do Python, não dependendo de pacotes externos.

### 7.4 Há operações que podem apagar ou sobrescrever dados?

O código utiliza `shutil.move()`, que altera a localização dos arquivos. Antes da movimentação existe a checagem:
`if os.path.exists(caminho_final):`
Garantindo que arquivos de mesmo nome no destino não sejam sobrescritos. Não há instruções para deleção.

### 7.5 O código utiliza dados sensíveis?

Não. Funciona apenas localmente com nomes de caminhos/arquivos e não lida com credenciais ou dados sigilosos.

### 7.6 Há tratamento de erros?

Sim, através de blocos `try/except` para lidar com permissões de acesso ou falhas ao mover arquivos.

### 7.7 Existem casos que o código não considera?

Casos a se considerar:

* arquivos ocultos;

* nomes com caracteres não usuais;

* permissões insuficientes de escrita;

* arquivos bloqueados por processos em execução.

## 8. Casos de teste

### Teste 1 — Caso normal

* **Objetivo:** verificar a organização por diferentes extensões.

* **Entrada:**

  ```
  trabalhos/
  ├── documento.pdf
  ├── imagem.jpg
  ├── foto.png
  ├── anotacao.txt
  └── planilha.xlsx
  ```

* **Resultado esperado:** cada arquivo movido para a subpasta da extensão correspondente.

* **Resultado obtido:** arquivos movidos corretamente.

* **Status:** Aprovado.

### Teste 2 — Caso limite

* **Objetivo:** testar comportamento com diretório vazio.

* **Entrada:** `pasta_vazia/`

* **Resultado esperado:** alerta de ausência de arquivos e encerramento seguro.

* **Resultado obtido:** *"A pasta está vazia ou não contém arquivos para organizar."*

* **Status:** Aprovado.

### Teste 3 — Caso de erro

* **Objetivo:** testar comportamento para caminho inexistente.

* **Entrada:** `pasta_inexistente`

* **Resultado esperado:** aviso de caminho não localizado sem crash do sistema.

* **Resultado obtido:** *"Erro: O caminho 'pasta_inexistente' não foi encontrado ou não é uma pasta válida."*

* **Status:** Aprovado.

### Resumo dos testes

| Teste | Tipo | Resultado | Status | 
| ----- | ----- | ----- | ----- | 
| **1** | Caso normal | Arquivos organizados por extensão | **Aprovado** | 
| **2** | Caso limite | Mensagem de pasta sem arquivos | **Aprovado** | 
| **3** | Caso de erro | Mensagem de caminho inválido | **Aprovado** | 

## 9. Problemas encontrados

Pontos de melhoria identificados:

* A função principal concentra múltiplas responsabilidades;

* Algumas operações podem ser extraídas para funções auxiliares;

* A variável `nome_base` é declarada mas não utilizada;

* Tratamento de exceções genéricas (`Exception`) poderiam ser refinadas.

## 10. Prompt de refatoração

```
Revise o código Python abaixo.

O programa já foi testado e funciona corretamente. Ele organiza automaticamente arquivos de uma pasta em subpastas de acordo com suas extensões.

Agora analise o código considerando:

- clareza;
- organização;
- duplicação de código;
- nomes de variáveis e funções;
- tratamento de erros;
- facilidade de manutenção;
- segurança para evitar sobrescrita de arquivos.

Não altere o comportamento esperado do programa.

Apresente:

1. Os problemas ou pontos que podem ser melhorados.
2. Sugestões de melhoria.
3. O código refatorado completo.
4. Uma explicação das principais alterações realizadas.
5. Confirme se os três casos de teste anteriores continuam sendo atendidos.
```

## 11. Código refatorado

> **Observação:** Esta etapa deve conter a versão gerada após a execução do prompt de refatoração.

```python
# Cole aqui a versão refatorada após a análise da IA.
```

## 12. Comparação

| Critério | Inicial | Refatorado | 
| ----- | ----- | ----- | 
| **Funcionamento correto** | 5 | *A avaliar* | 
| **Clareza** | 4 | *A avaliar* | 
| **Organização** | 4 | *A avaliar* | 
| **Legibilidade** | 4 | *A avaliar* | 
| **Tratamento de erros** | 4 | *A avaliar* | 
| **Facilidade de manutenção** | 4 | *A avaliar* | 

## 13. Reflexão

* **Onde a IA mais ajudou?**

  Na estrutura inicial, explicação de funções de bibliotecas como `os`/`shutil` e identificação de tratamentos de exceção.

* **Onde a IA errou?**

  Apesar de funcional, gerou variáveis não utilizadas (`nome_base`) e unificou tarefas de leitura, validação e movimentação em apenas uma grande função.

* **O que precisei modificar?**

  Ajustes finos no tratamento das mensagens ao usuário e separação lógica a ser validada pós-refatoração.

* **Consigo explicar o código?**

  Sim, o fluxo de listar o diretório, isolar a extensão, validar se a subpasta existe e mover o arquivo sem sobreposição está compreendido.

## 14. Take Away

> Programar com IA não significa deixar a IA programar por mim. Significa utilizar a Inteligência Artificial como uma ferramenta de apoio, compreendendo, testando, corrigindo, validando e documentando o código produzido.

### Cinco regras para utilizar IA de maneira responsável

1. **Compreender** o código antes de utilizá-lo.

2. **Testar** a solução antes de considerá-la pronta.

3. **Verificar** possíveis erros e riscos de segurança.

4. **Não compartilhar** senhas, tokens, chaves ou dados confidenciais.

5. **Assumir responsabilidade** pelo código utilizado.

## 15. Conclusão

A atividade demonstrou o papel da IA no desenvolvimento de rotinas de automação. A solução atende ao escopo proposto garantindo segurança ao usuário através das validações implementadas.

## Checklist da atividade

* [x] Defini o problema.

* [x] Identifiquei entrada, processamento e saída.

* [x] Registrei o prompt utilizado.

* [x] Registrei a primeira versão do código.

* [x] Analisei criticamente a solução.

* [x] Executei três tipos de teste.

* [x] Registrei os resultados dos testes.

* [x] Solicitei uma refatoração.

* [ ] Registrei o código refatorado.

* [ ] Comparei as duas versões após a refatoração.

* [x] Respondi à reflexão final.

* [x] Organizei o documento para registro no GitHub.