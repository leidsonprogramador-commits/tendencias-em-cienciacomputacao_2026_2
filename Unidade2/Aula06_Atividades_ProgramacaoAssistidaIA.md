Aula 06 – Programação Assistida por Inteligência Artificial

Atividades: Leitura orientada, discussão em grupo e estudo de caso

Texto-base: Vibe coding: programming through conversation with artificial intelligence — Advait Sarkar e Ian Drosos (PPIG 2025)

Disciplina: Tendências em Ciência da Computação
Unidade: II — Programação Assistida
Instituição: Centro Universitário UDF

0. Códigos da pesquisa e identificação das evidências

O artigo de Sarkar e Drosos (2025) analisou inicialmente 35 vídeos publicados no YouTube e na Twitch sobre vibe coding. Desse conjunto, cinco vídeos, totalizando 8 horas e 27 minutos, foram selecionados para uma análise detalhada utilizando o método de framework analysis.

Os códigos apresentados a seguir identificam as principais evidências utilizadas pelos pesquisadores e citadas neste documento.

Código	Vídeo ou contexto	Plataforma	Duração
TW1	!foony | VIP | Vibe Coding | !idea — desenvolvimento de funcionalidades exclusivas para membros de um site de games existente	Twitch	05:30:50
YT15	VIBE CODING with CURSOR – Draw w/ HTML and JS — criação de um diagrama animado para explicar o fluxo de trabalho de um agente de código	YouTube	00:17:45
YT21	Vibe Coding with AI: Watch me fix a chat interface in real-time — correção de uma aplicação de chat integrada ao GitHub	YouTube	01:29:37
YT22 / YT22b	Vibe Coding Startup Using Most Advanced AI — Phase 1 e 2 — desenvolvimento de uma aplicação web para auxiliar estudantes internacionais em candidaturas a empregos	YouTube	00:32:05 + 00:37:02

O estudo organizou os resultados em nove categorias: objetivos (goals), intenções (intentions), fluxo de trabalho (workflow), elaboração de prompts (prompting), depuração (debugging), desafios (challenges), conhecimento especializado (expertise), confiança (trust) e definição e desempenho (definition and performance).

Essas categorias ajudam a compreender como os desenvolvedores utilizam ferramentas de inteligência artificial, quais dificuldades encontram e como mantêm o controle sobre o código produzido.

1. Trechos e ideias registrados durante a leitura individual
1.1 Confiança na inteligência artificial

O artigo demonstra que a confiança na inteligência artificial durante o vibe coding não deve ser absoluta. Ela é gradual, dinâmica e depende do contexto, da tarefa executada e da qualidade dos resultados apresentados pela ferramenta.

No vídeo YT21, o desenvolvedor utiliza a IA para acelerar o processo de programação, mas revisa as alterações sugeridas para manter o controle sobre o sistema. Já no vídeo YT22, o criador reforça que não se deve seguir cegamente as recomendações da inteligência artificial, pois ela deve ser entendida como uma ferramenta de apoio.

Dessa forma, a confiança precisa ser construída por meio de testes, revisões e verificações contínuas, e não apenas pela aparência de qualidade do código gerado.

1.2 Conhecimento especializado

Outro achado importante do artigo é que a inteligência artificial não elimina a necessidade de conhecimento técnico. Em vez disso, ela transforma a maneira como esse conhecimento é utilizado.

O desenvolvedor deixa de se concentrar exclusivamente na escrita manual de cada linha de código e passa a exercer funções de orientação, revisão e avaliação dos resultados produzidos pela IA.

Essa mudança exige a capacidade de selecionar ferramentas adequadas, avaliar rapidamente o código gerado e identificar situações em que a intervenção manual é necessária.

Nos vídeos YT21 e YT15, essa prática aparece na leitura rápida do código, também chamada de leitura por varredura ou avaliação geral (gestalt). O desenvolvedor procura identificar estruturas, nomes de funções, chamadas de API e possíveis inconsistências sem necessariamente analisar cada linha de forma isolada.

Entretanto, essa leitura inicial não substitui uma revisão aprofundada quando a tarefa envolve segurança, arquitetura ou lógica de negócio crítica.

2. Respostas às questões norteadoras
2.1 Até que ponto podemos confiar no código produzido pela IA?

A confiança no código gerado por inteligência artificial deve ser baseada em verificações sucessivas. Mesmo quando o resultado parece correto, é necessário confirmar se ele funciona adequadamente, atende aos requisitos e não introduz problemas no sistema.

Antes de aceitar o código produzido por uma IA, recomenda-se:

Executar e testar a aplicação: verificar o comportamento real do sistema, em vez de confiar apenas na aparência do código. Essa prática foi observada nos vídeos analisados, incluindo TW1, YT15, YT21 e YT22.
Revisar as alterações realizadas: examinar os diffs para identificar mudanças inesperadas, funções inadequadas e chamadas incorretas.
Consultar a documentação: confirmar se as APIs, bibliotecas e métodos utilizados realmente existem e são compatíveis com o projeto.
Investigar os erros: utilizar ferramentas como o console do navegador e o terminal para formular hipóteses e compreender as causas dos problemas, como observado nos vídeos YT21 e YT22.
Verificar a integração com o sistema: avaliar se o código respeita a arquitetura existente e não compromete outras funcionalidades.

Aceitar código sem revisão, testes ou compreensão pode gerar diversos riscos, como:

Uso de APIs inexistentes ou incorretas, decorrente de informações inventadas pelo modelo.
Inclusão de dependências desnecessárias, desatualizadas ou inseguras.
Introdução de vulnerabilidades, como injeção de SQL e cross-site scripting (XSS).
Produção de código difícil de compreender, corrigir e manter.
Perda de conhecimento sobre o funcionamento do próprio sistema, dificultando futuras alterações.

No vídeo TW1, por exemplo, é levantada a preocupação de que um desenvolvedor com pouca experiência talvez não conseguisse corrigir o código produzido. Isso evidencia que a velocidade de geração não garante facilidade de manutenção.

Portanto, a IA pode contribuir para aumentar a produtividade, mas a qualidade do resultado depende da capacidade humana de verificar, compreender e validar o código antes de incorporá-lo ao projeto.

2.2 A IA reduz a necessidade de conhecimento em programação ou transforma o tipo de conhecimento necessário?

A inteligência artificial transforma a aplicação do conhecimento em programação, mas não elimina a necessidade de experiência técnica. O desenvolvedor passa a dedicar parte de seu trabalho à orientação da ferramenta e à avaliação das soluções produzidas.

Nesse contexto, destacam-se três áreas de conhecimento.

1. Conhecimento técnico tradicional

Continua sendo necessário para compreender código, depurar erros complexos, projetar arquiteturas e avaliar os impactos das alterações no sistema. Também é fundamental para tomar decisões relacionadas à segurança, ao desempenho e à manutenção.

2. Conhecimento sobre inteligência artificial

Envolve compreender as limitações dos modelos, selecionar ferramentas adequadas, formular bons prompts e reconhecer quando as respostas podem estar incorretas ou incompletas.

3. Conhecimento sobre o produto e suas necessidades

Consiste em transformar objetivos do negócio em funcionalidades, avaliar se as soluções propostas atendem aos requisitos e decidir quais sugestões devem ser mantidas, modificadas ou descartadas.

Com isso, o programador assume cada vez mais o papel de orientador, avaliador e revisor do código. Essa atuação exige pensamento crítico, capacidade de formular hipóteses diante de erros e discernimento para identificar quando uma análise superficial é suficiente e quando é necessário realizar uma revisão detalhada.

Assim, a IA pode reduzir o esforço necessário para determinadas tarefas de implementação, mas aumenta a importância da capacidade de avaliar soluções e assumir decisões técnicas fundamentadas.

2.3 Quando é melhor utilizar a IA e quando é melhor assumir o controle manualmente?

A escolha entre utilizar a inteligência artificial ou realizar uma tarefa manualmente depende da complexidade, dos riscos envolvidos e do esforço necessário para orientar a ferramenta.

A tabela a seguir apresenta situações em que cada abordagem tende a ser mais adequada.

Delegar à IA	Trabalhar manualmente
Gerar código repetitivo e estruturas básicas (boilerplate)	Definir a arquitetura do sistema e avaliar alternativas técnicas
Criar implementações iniciais por meio de prompts	Realizar pequenas alterações que podem ser feitas mais rapidamente na IDE
Gerar testes unitários para cenários comuns e situações de falha	Implementar e validar regras de negócio críticas
Produzir documentação e explicar trechos de código legado	Revisar segurança, privacidade e questões éticas
Explorar ideias e desenvolver protótipos iniciais, como no vídeo YT15	Investigar erros complexos que exigem hipóteses e análise causal, como nos vídeos YT21 e YT22
Sugerir alternativas de implementação	Tomar decisões finais sobre qualidade, manutenção e integração

Um critério importante é comparar o esforço de orientar a IA com o esforço de executar a tarefa diretamente. Quando elaborar, testar e corrigir um prompt consome mais tempo do que realizar a alteração manualmente, a edição direta tende a ser a opção mais eficiente.

Essa situação é ilustrada nos vídeos TW1 e YT21, nos quais a intervenção manual pode ser mais adequada para determinadas alterações pontuais.

Portanto, a melhor estratégia não consiste em utilizar a IA para todas as tarefas, mas em identificar onde ela oferece ganhos reais de produtividade sem comprometer a qualidade e o controle do sistema.

3. Estudo de caso
3.1 Situação apresentada

Uma equipe de desenvolvimento aceita a implementação completa de uma funcionalidade produzida por inteligência artificial. O código foi testado apenas superficialmente, sem revisão adequada das dependências, da segurança, da manutenibilidade ou dos impactos sobre outras partes do sistema.

Essa situação representa um risco porque o funcionamento aparente de uma funcionalidade não garante que ela seja segura, confiável ou compatível com os requisitos do projeto.

3.2 Ações recomendadas antes da incorporação do código

Antes de integrar a implementação ao projeto principal, a equipe deve executar as seguintes ações:

Aplicar um checklist de qualidade: verificar se o código atende aos requisitos, trata casos extremos, segue os padrões do projeto e apresenta uma estrutura compreensível.
Realizar análises de segurança: utilizar ferramentas de análise estática e dinâmica, como SAST e DAST, além de verificar a validação e a sanitização dos dados de entrada.
Criar testes automatizados: desenvolver testes unitários, testes de integração e testes de regressão para verificar o comportamento esperado e identificar possíveis efeitos colaterais.
Verificar as dependências: analisar as bibliotecas adicionadas, suas versões, suas vulnerabilidades conhecidas e suas licenças de uso.
Solicitar uma revisão por pares: submeter o código à avaliação de outros desenvolvedores, utilizando critérios de qualidade equivalentes aos aplicados ao código escrito manualmente.
Documentar as decisões técnicas: registrar os motivos da abordagem escolhida, suas limitações e os principais riscos identificados.
Validar a integração: confirmar que a funcionalidade não prejudica outras partes do sistema e que seu comportamento está de acordo com os requisitos.

A incorporação do código deve ocorrer somente após a avaliação dos resultados dessas verificações e a correção dos problemas identificados.

3.3 Responsabilidades que permanecem humanas

Mesmo com o apoio da inteligência artificial, algumas responsabilidades continuam exigindo decisão e supervisão humanas:

Definir e avaliar a arquitetura do sistema.
Analisar os riscos de segurança e privacidade.
Avaliar os impactos das alterações em outras funcionalidades.
Verificar a conformidade com requisitos legais, éticos e de licenciamento.
Decidir se o código atende aos critérios de qualidade do projeto.
Assumir a responsabilidade profissional pelas decisões de desenvolvimento e pela aprovação das alterações.

A IA pode auxiliar na análise dessas questões, sugerir soluções e automatizar verificações. Entretanto, suas recomendações não substituem a avaliação crítica nem a responsabilidade das pessoas envolvidas no desenvolvimento.

4. Três boas práticas para a colaboração entre humanos e IA
4.1 Compreender o código antes de aceitá-lo

O desenvolvedor deve ser capaz de explicar o funcionamento da implementação, identificar suas principais dependências e compreender as decisões técnicas envolvidas.

Quando o código gerado não é compreendido, o ideal é interromper a integração e investigar os trechos desconhecidos antes de prosseguir. Essa prática favorece a transparência e reduz a dependência excessiva da ferramenta.

4.2 Testar e verificar continuamente

O código gerado pela IA deve ser submetido a testes e revisões antes de ser utilizado em um ambiente real.

É importante validar o comportamento da aplicação, analisar possíveis erros e confirmar se a solução atende aos requisitos. A confiança deve resultar da verificação dos resultados, e não apenas da segurança demonstrada pela resposta da ferramenta.

4.3 Definir claramente os papéis humanos e da IA

A inteligência artificial pode ser utilizada para tarefas repetitivas, geração de estruturas iniciais, documentação e exploração de alternativas.

Ao desenvolvedor cabe orientar o processo, avaliar os resultados e tomar decisões críticas sobre arquitetura, regras de negócio, segurança e manutenção.

Essa divisão permite aproveitar os benefícios da automação sem abrir mão do controle técnico e da responsabilidade humana.

5. Síntese final

A programação assistida por inteligência artificial modifica a maneira como o software é desenvolvido, permitindo acelerar determinadas tarefas e explorar soluções com maior agilidade. Entretanto, os benefícios dessa abordagem dependem da capacidade do desenvolvedor de compreender, revisar e validar os resultados produzidos.

O conceito de vibe coding evidencia que programar por meio de conversas com a IA não significa abandonar o conhecimento técnico. Pelo contrário, exige novas competências relacionadas à elaboração de prompts, à avaliação rápida de código, à identificação de erros e à escolha do momento adequado para intervir manualmente.

A confiança na inteligência artificial deve ser construída por meio de testes, revisões e verificações contínuas. Código aparentemente correto pode conter erros, vulnerabilidades ou decisões inadequadas que comprometam a manutenção e a segurança do sistema.

Portanto, a colaboração responsável entre humanos e IA depende de uma divisão consciente de tarefas. A ferramenta pode contribuir para a geração de código e para a automatização de atividades, enquanto o desenvolvedor permanece responsável pela avaliação crítica, pelas decisões técnicas e pela aprovação final da implementação.

Em síntese, programar com inteligência artificial de maneira responsável significa manter uma compreensão ativa do sistema, questionar os resultados produzidos e reconhecer que a produtividade não elimina a necessidade de qualidade, segurança e responsabilidade humana.

Referências

SARKAR, Advait; DROSOS, Ian. Vibe coding: programming through conversation with artificial intelligence. PPIG, 2025.

RITCHIE, Jane; SPENCER, Liz. Qualitative data analysis for applied policy research. In: HUBERMAN, A. Michael; MILES, Matthew B. (org.). The Qualitative Researcher's Companion. 2002.

UDF — Centro Universitário UDF. Guia de Boas Práticas na Colaboração Humano-IA. Material didático da disciplina, elaborado pela Prof.ª Kadidja Valéria.

Observação: recomenda-se conferir os dados bibliográficos completos das obras e do guia didático antes da entrega final do trabalho.
