Aula 02 — Engenharia de Prompt
1. Identificação

Data: 21/08/2026

Integrantes:

Leandro Alcântara Morais (RGM: 41160291)
Leidson Arthur Santana Almeida (RGM: 38222345)
2. Problema escolhido

Desenvolver o núcleo lógico de um software de organização de estudos. O desafio central é calcular as horas de estudo diárias necessárias.

Se o usuário digitar 0 dias ou valores inválidos, ocorre o erro clássico ZeroDivisionError, quebrando o programa.

3. Objetivo

Criar e refinar um algoritmo em Python para o ecossistema do software de estudos.

O foco é garantir:

Tratamento rigoroso de erros;
Tipagem de dados (PEP 484);
Prevenção de falhas;
Aplicação de boas práticas de Sistemas de Informação.
4. Prompt inicial

Crie uma função em Python para o meu software de estudos. Ela deve receber o total de horas que preciso estudar e a quantidade de dias que faltam até a prova, e retornar quantas horas preciso estudar por dia.

Resultado inicial
def calcular_horas_diarias(total_horas, dias_restantes):
    horas_por_dia = total_horas / dias_restantes
    return horas_por_dia

5. Análise crítica
O que funcionou

A operação aritmética de divisão foi executada de forma correta.

O que não funcionou

Ocorreu uma falha fatal (crash) do sistema se dias_restantes = 0.

O que faltou
Validação de entradas negativas;
Tratamento explícito de exceções;
Tipagem de dados.
O que precisa ser validado

Verificar se o backend barra entradas inválidas antes de realizar o cálculo.

6. Desenvolvimento das Variações de Prompt
🔴 Variação 1 — Foco Didático

Objetivo: Ensinar passo a passo o tratamento de erros.

Prompt:

Atue como um Tutor de Programação em Python. Melhore a função anterior explicando passo a passo como tratar o erro de divisão por zero (ZeroDivisionError) e como garantir que o programa não quebre caso o usuário digite um valor inválido na plataforma de estudos.

Resposta da IA:

def calcular_horas_diarias_segura(total_horas, dias_restantes):
    if total_horas < 0 or dias_restantes < 0:
        return "Erro: Os valores não podem ser negativos."
    try:
        return total_horas / dias_restantes
    except ZeroDivisionError:
        return "Erro: O número de dias restantes não pode ser zero."

🔵 Variação 2 — Foco em Performance

Objetivo: Otimizar cálculos em lote com list comprehension.

Prompt:

Com o objetivo de deixar o motor do software de estudos mais rápido e performático, otimize o programa em Python usando compreensão de listas (list comprehension) para calcular as horas diárias de uma lista de diferentes matérias de uma só vez. Formato de saída: apenas o bloco de código.

Resposta da IA:

materias = [(20, 5), (15, 3), (10, 2)]
horas_calculadas = [(h / d if d > 0 else 0) for h, d in materias if h >= 0]
print(horas_calculadas)  # Saída: [4.0, 5.0, 5.0]

7. Prompt final refinado

Escreva um sistema em Python para organização de estudos que ajude estudantes a organizarem sua rotina. Preciso da função principal desse sistema.

Regras do sistema:

A função calcula a meta de horas diárias de estudo. Ela deve receber o total de horas de estudo necessárias e quantos dias faltam até a prova.
Implemente tratamento de erros para dados inválidos (como o usuário digitar 0 dias ou valores negativos). Evite travamentos tratando a exceção ZeroDivisionError com try/except.
Siga a Heurística de Usabilidade nº 5 de Jakob Nielsen (Prevenção de Erros).
Use Type Hinting (PEP 484) e comentários simples, aplicando Clean Code.
O resultado final deve ser arredondado para 1 casa decimal (ex: 2.5).
8. Resultado final obtido
from typing import Union


def calcular_meta_diaria(
    total_horas: Union[int, float],
    dias_restantes: int
) -> float:
    """
    Calcula a meta de horas diárias de estudo.

    Parâmetros:
    total_horas (int | float): Total de horas de estudo necessárias.
    dias_restantes (int): Quantos dias faltam até a prova.

    Retorno:
    float: Meta de horas por dia, arredondada para 1 casa decimal.
    """
    try:
        if total_horas <= 0:
            raise ValueError("O total de horas deve ser maior que zero.")

        if dias_restantes <= 0:
            raise ValueError("O número de dias deve ser maior que zero.")

        meta_diaria = total_horas / dias_restantes
        return round(meta_diaria, 1)

    except ZeroDivisionError:
        print("Erro: número de dias não pode ser zero.")
        return 0.0

    except ValueError as ve:
        print(f"Entrada inválida: {ve}")
        return 0.0

    except Exception as e:
        print(f"Ocorreu um erro inesperado: {e}")
        return 0.0

9. Técnicas utilizadas
Role Prompting
Few-Shot Prompting
Contexto
Restrições
Formato de saída
Prompt em etapas
Refinamento iterativo
10. Comparação
Inicial

Função insegura e suscetível a falhas críticas em tempo de execução.

Intermediário

Abordagem focada em explorar a didática conceitual e a performance de processamento em lote.

Final

Unificação completa das melhores práticas de mercado, garantindo robustez corporativa, prevenção de erros e padronização ideal para o consumo do front-end.

11. Validação

Testes estruturados foram realizados simulando cenários extremos com:

Entradas nulas;
Valores negativos;
Divisão por zero.

Todas as exceções foram capturadas e tratadas perfeitamente, retornando o valor padrão 0.0 sem interromper a execução do backend.

12. Ética e responsabilidade — Reflexão Ética
Qual é a principal responsabilidade de um profissional de tecnologia que utiliza IA generativa?

Auditar tecnicamente tudo o que é gerado.

A IA opera por probabilidade estatística e pode omitir tratamentos cruciais de segurança. A responsabilidade legal e ética por quaisquer bugs e vulnerabilidades de código implantados é
