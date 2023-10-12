# WEEK 2 - Fine Tuning

## Instruction fine-tuning
* *prompt enginering* pode ser visto como um  *fine tuning* (instruction), onde todos os pesos são reajustados ("full fine tuning")
* Existem templates para prompts
* Podemos construir modelos de análise de sentimentos dessa maneira

## Fine-tuning on a single task
* Enviar vários exemplos para *task*, isso geralmente melhorar a perfomance naquela *task*, porém pode gerar "esquecimento" do modelo, ou seja em outras tarefas, ele perde a eficiência.
* Podemos tentar evitar *forgetting* fazendo um fine-tune de multiplas *tasks* ao mesmo tempo

## Multi-task fine-tuning 
* Muito exemplos, com exemplo para treinamento para cada *task*
* **FLAN (Fine-tuned LAnguage Net)** refere-se a um conjunto especifico de intruções utilizado para *instruction fine-tuning*
* FLAN-T5 é um bom modelo de proposito geral, é a versão FLAN do T5

## Model Evaluation
* unigram: uma palavra
* n-gram: conjutno de n palavras
### Rouge
* Utilizado para sumarização de texto, compara o resumo com um ou mais resumos de referência

#### Rouge-1 (individual words)
* Métricas para uma palavra, não considera ordem nem contexto

$$\text{Recall} = \dfrac{# unigram matches in output }{#unigrams in reference} \quad \text{# = cardinalidade}$$


$$\text{Precision} = \dfrac{# unigram matches in output }{#unigrams in output} \quad \text{# = cardinalidade}$$



* Podemos usar bi-gramas também, estendendo 1 a 1 as palavras para criar os bi-gramas

#### Rouge-L

* *Longest common subsequence(LCS)* entre a referencia humana (prompt)  e o output do modelo

* E utilizamos o LCS no numerador da precisão e recall

$$\text{Precision} = \dfrac{# \text{LCS(Gen, Ref)}}{#unigrams in output} \quad \text{# = cardinalidade}$$

* Quando temos um output repetindo palavras, as métricas anteriores vão geralmente aumentar, mesmo o output não fazendo sentido, dessa maneira utilizamos uma função *clip*.

* *clip*: Limita o *unigram matches* pelo máximo de vezes que a palavra aparece na *reference*

### Bleu Score
* *Bilingual evalution under study*

* Utilizado para tradução de texto, compara com uma tradução humana
* *Blue metric* = Avg(precisão no range de n gramas) 

* Ou seja, calcular a precisão pra todos os **n** possíveis n-gramas

## Benchmark
* Existem alguns "padrões" de datasets para testar a performance de LLM's

-------
# Fundamentos
Escritas sobre conceitos básicos/fundamentais para NLP.

## Word Embedding

## RNN

## LSTM
