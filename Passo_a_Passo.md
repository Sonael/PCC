## AFEX

1. Escreva plug-ins de injeção de falhas. Esses são pequenos trechos de código Java necessários para encapsular cada ferramenta injetora de falhas a ser usada (aproximadamente 150 linhas de código).
 
2. Escolha o espaço de falha. O desenvolvedor deve escrever um arquivo descritor de espaço de falha (usando a linguagem especificada na Fig. 3). Descobrimos que a maneira mais simples de chegar a essa descrição é analisar o sistema alvo S com um rastreador como o ltrace, ou usar uma ferramenta de análise estática, como o profiler que acompanha o LFI [17].
 
3. Métrica de impacto do projeto. A métrica de impacto orienta o algoritmo de exploração. A maneira mais fácil de projetar a métrica é alocar pontuações para cada evento de interesse, como 1 ponto para cada bloco básico recém-coberto, 10 pontos para cada bug encontrado, 20 pontos para cada falha, etc.
 
4. Forneça conhecimento de domínio. Opcionalmente, o desenvolvedor pode fornecer conhecimento do domínio AFEX de várias maneiras. Por exemplo, se o sistema em teste for implantado em um ambiente de produção com armazenamento altamente confiável, pode fazer sentido fornecer um modelo de relevância de falhas no qual as falhas de E/S sejam consideradas menos relevantes (uma vez que são menos prováveis de ocorrer em prática), a menos que tenham um impacto catastrófico em S. Isso desencorajará a AFEX de explorar falhas de pouco interesse.

5. Escreva scripts de teste. Os desenvolvedores devem fornecer três scripts: inicialização, teste e limpeza. Esses são scripts simples e podem ser escritos em qualquer linguagem de script suportada nos nós do trabalhador.

6. testes executados ou após um determinado limite ser atingido em termos de cobertura de código, bugs encontrados, etc.

7. Execute AFEX. AFEX agora está pronto para começar. Ele fornece métricas de progresso em um log, para que os desenvolvedores possam acompanhar sua execução, caso desejem.

8. Analise os resultados. AFEX produz tabelas com medidas para cada teste (adequação, caracterização de qualidade, etc.) e identifica um teste representativo para cada cluster de redundância (conforme descrito em §5). AFEX também cria uma pasta para cada teste, contendo logs, core dumps ou qualquer outra saída produzida durante o teste.


## Xception

**Utilizando um processador MPC601**

![Xception](/images/xception.png)