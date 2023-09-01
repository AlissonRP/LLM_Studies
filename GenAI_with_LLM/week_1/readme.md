## Week 1  - Introduction To LLMs and Generative AI

* Geralmente o output do modelo (de linguagem) é chamado de *completion*

* Utilizar o modelo para gerar texto é dito *inference*

* *language undestanding* aumenta com a quantidade de parâmetros do modelo?

* É importante manter sempre o mesmo *tokenizer*

* O texto enviado para o modelo é dito *prompt*

### Parameters
* **Max new Tokens**: Vai limitar a quantidade de palavras no *output* do modelo.
* 
* *greddy*: A palavra/token com maior probabilidade é selecionada
* *Random Sampling*: Seleciona aleatoriamente, utilizando as probabilidades da camada final como pesos
* Sample top K: Faz o *Random Sampling* somente dos **k** tokens com maior probabilidade
* Sample top P: Faz *Random Sampling* pelos tokens ordenados a quais a probabilidade acumulada deles não ultrapassa **P**
* Temperature: Altera a forma da distribuição que gera o próximo token (ou seja é parametro de escala). Valores pequenos (<1) tornam a distribuição mais concentrada, ou seja o modelo torna-se menos "criativo" (menos aleatório).

## Lifecycle

* **Scope**: Definir precisamente o problema de negócio (task) a qual o LLM irá efetuar seu trabalho
* **Select**: Escolher um modelo, ou treinar o seu próprio (geralmente utiliza-se um pré-treinado)
* **Adapt and Align Model**: Aqui entra o *prompt engineering*, *fine-tuning* e alinhar com o *feedback* humano (RLHF) , e por fim avaliar o modelo.
* **Application Integration**: Optimizar o modelo para *deploy*, e cuidar dos requisitos para acoplar a aplicação.


*  O que ainda não tenho bom domínio para explicar: Encoder, Decoder, Self-Attention (ou seja modelos variocionais)

* Existem modelos que possuem somente um encoder (*encoder only*), BERT é um exemplo. Dessa maneira tbm existem os somente  com *decoder*, os mais conhecidos atualmente (2023), exemplo são as familias de GPT e LLama.


## Considerações para escolher/treinar um modelo

* LLM são originalmente treinados em uma vasta quantidade de data não estruturados (self-supervised)
* Nem todos os tokens são utilizados para o treino após o *data quality*

### Autoenconding models

* O objetivo do treino é reconstruir a "sentença" de input (masked language modeling)
* O modelo "entende" todo o contexto e não somente a ordem
* São bons para análise de sentimentos, word classification

### Autoregressive Models (Decoder-only)
* O objetivo é prever o próximo token baeado nos anteriores
* Os modelos "escondem" a sequência de input e depois eles prevem o proximo 1 a 1
* É diferente do encoding pq é unidirecional, o modelo preve o proximo token baseado em outros exemplos
* São bons para geração de texto (GPT)


### Sequence - to - Sequence (encoder e decoder)

* Úteis quando vc tem texto de input e output


## Desafios Computacionais 

* 1 Parametro = 4bytes
* 1b parametros = 4gb

E além dos pesos sao necessários guardar:

* Optimizadores (8 bytes por parâmetro)
* Gradientes (4 bytes por parâmetro)
* Ativações e usos temporários de memórias(variáveis) (8 bytes por parametro)

Ou seja é mais ou menos 80gb de memória para ajustar um modelo de 1b de parâmetros


### Quantization
* Diminuir a precisão de 32float para 16
* Em outras palavras é uma projeção do FP32 para FP16 no caso de floats
* E existem outras maneiras de otimizar um FP16, como por exemplo o BFLOAT16 (B para Brain), é um hibrido do FP'6 e FP32, basicamente um FP32 truncado
* 
* 
 
Para os armazenamento de parâmetros, reduz em torno de 50% do uso necessário de ram

## Optimizando
* Podemos aumentar o tamanho do dataset, ou parâmetros(ou ambos). Porém estamos sempre limitado aos recursos computacionais
* Paper's Importantes: *Scaling Laws for Neural Language Models*, *Training Compute-Optimal LLM*
* ***Muitos LL podem estar *over-parameterized* e *under-trained***
* Modelos menores (parametros) treinados com mais dados podem performar melhor?
* **Compute-optimal of token (~20x o numero de parâmetros)**


## Domain Adaptation
