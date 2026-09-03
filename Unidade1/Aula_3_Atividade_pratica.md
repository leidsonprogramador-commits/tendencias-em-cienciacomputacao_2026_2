Atividade - Refinamento de Prompts
Identificação
Nome: [Seu nome]
Turma: [Sua turma]
Data: 03/09/2026
Ferramenta de IA utilizada: ChatGPT
1. Problema escolhido
Contexto

A programação é uma das áreas fundamentais da Ciência da Computação. Para iniciantes, alguns conceitos podem ser difíceis de compreender quando são apresentados apenas por meio de definições técnicas. Um exemplo é o conceito de recursão, que envolve uma função chamar a si mesma para solucionar um problema.

Problema

Como utilizar diferentes níveis de refinamento de prompts para obter uma explicação mais clara, adequada e útil sobre recursão para uma pessoa que está começando a estudar programação?

Objetivo

Utilizar uma IA generativa para explicar o conceito de recursão de maneira progressiva, comparando diferentes prompts e analisando como informações sobre público, contexto, formato e critérios modificam a qualidade da resposta.

2. Prompt 1 - Versão inicial
Prompt
Explique o que é recursão em programação.

Resultado 1

Recursão é uma técnica de programação na qual uma função chama a si mesma para resolver um problema. Normalmente, uma função recursiva possui dois elementos principais: um caso base, que determina quando a função deve parar, e um caso recursivo, no qual a função chama a si mesma com um problema menor.

Por exemplo, podemos calcular o fatorial de um número usando recursão:

def fatorial(n):
    if n == 0:
        return 1
    return n * fatorial(n - 1)


Nesse exemplo, n == 0 é o caso base. Quando essa condição é atingida, a função para de chamar a si mesma. Caso contrário, ela calcula n * fatorial(n - 1).

A recursão é utilizada em diversos problemas computacionais, especialmente em estruturas de dados e algoritmos, como árvores, busca em profundidade e algoritmos de divisão e conquista.

Primeira impressão
O que funcionou?
A resposta apresentou uma definição correta de recursão.
Foram apresentados os conceitos de caso base e caso recursivo.
O exemplo em Python ajudou a relacionar a explicação com a prática.
Foram citadas algumas aplicações da recursão.
O que faltou?
A explicação poderia ser mais acessível para alguém sem experiência em programação.
Não houve uma explicação detalhada de como as chamadas da função acontecem.
Poderia existir uma analogia com uma situação do cotidiano.
O exemplo poderia ser explicado passo a passo.
O que ficou genérico?

A parte sobre aplicações da recursão apresentou exemplos sem explicar como a recursão é utilizada em cada um deles.

O que poderia ser melhor?

Seria interessante informar à IA que o público é iniciante, solicitar uma explicação progressiva, incluir uma analogia e explicar a execução do código passo a passo.

3. Prompt 2 - Primeiro refinamento
Alterações realizadas
Papel: Professor de programação para iniciantes.
Contexto: A explicação será utilizada em uma atividade introdutória de Ciência da Computação.
Objetivo: Ensinar o conceito de recursão de forma clara e prática.
Público: Estudantes iniciantes em programação.
Formato: Explicação em etapas, com analogia, exemplo de código e simulação da execução.
Restrições: Evitar excesso de termos técnicos e explicar qualquer termo necessário.
Critérios: A resposta deve ser clara, correta, didática e apresentar um exemplo simples.
Prompt
Atue como um professor de programação especializado em ensinar
Ciência da Computação para iniciantes.

Explique o conceito de recursão para estudantes que estão
começando a aprender programação e ainda possuem pouca experiência
com funções.

Comece com uma explicação simples e utilize uma analogia do
cotidiano para facilitar a compreensão.

Depois:

1. explique o que é uma função recursiva;
2. explique o que é caso base;
3. explique o que é caso recursivo;
4. apresente um exemplo simples em Python;
5. explique o código linha por linha;
6. mostre passo a passo como as chamadas recursivas acontecem.

Evite utilizar termos técnicos sem explicá-los.

Organize a resposta com títulos e exemplos.

O objetivo é que um estudante iniciante consiga explicar com suas
próprias palavras o que é recursão e por que o caso base é necessário.

Resultado 2
O que é recursão?

Recursão é uma técnica de programação em que uma função chama a si mesma para resolver um problema.

Uma maneira de imaginar isso é pensar em caixas dentro de caixas. Imagine que você tenha uma caixa grande e, dentro dela, existe outra caixa menor. Dentro da segunda caixa existe outra, e assim por diante. Para encontrar um objeto, você abre uma caixa e verifica se chegou à última. Quando chega à caixa que não possui outra dentro dela, você para.

Em uma função recursiva acontece algo parecido: a função continua chamando a si mesma até chegar a uma condição que determina que ela deve parar.

Caso base

O caso base é a condição responsável por interromper a recursão.

Sem ele, a função poderia continuar chamando a si mesma indefinidamente.

Caso recursivo

O caso recursivo é a parte da função que realiza uma nova chamada para ela mesma, geralmente utilizando um problema menor ou mais simples.

Exemplo em Python
def contar(n):
    if n == 0:
        return

    print(n)
    contar(n - 1)


Se executarmos:

contar(3)


A função realizará as seguintes chamadas:

contar(3)
   |
   v
contar(2)
   |
   v
contar(1)
   |
   v
contar(0)


Quando n chega a 0, a condição do caso base é verdadeira e a função para.

A saída será:

3
2
1

Como o código funciona?

Na primeira chamada:

contar(3)


O programa verifica se 3 é igual a 0. Como não é, imprime 3 e chama:

contar(2)


Depois acontece a mesma coisa:

contar(2)
contar(1)
contar(0)


Quando chega em contar(0), o programa encontra o caso base e não realiza outra chamada.

Resumindo

Uma função recursiva precisa, em geral, de:

Caso base: define quando parar.
Caso recursivo: define como continuar.

A recursão pode ser útil para resolver problemas que podem ser divididos em problemas menores semelhantes ao problema original.

4. Comparação entre Prompt 1 e Prompt 2
Critério	Prompt 1	Prompt 2
Clareza	3	5
Precisão	4	5
Relevância	3	5
Organização	3	5
Adequação ao público	2	5
Atendimento ao objetivo	3	5
Utilidade prática	3	5
Total	21	35

O Prompt 2 apresentou uma melhora significativa porque especificou o público, o papel da IA, o objetivo e a estrutura esperada para a resposta.

O primeiro prompt deixava grande parte dessas decisões por conta da IA. Já o segundo prompt reduziu as ambiguidades e indicou exatamente quais pontos deveriam ser abordados.

5. Prompt 3 - Segundo refinamento
O que estava inadequado na primeira resposta?

A primeira resposta estava tecnicamente
