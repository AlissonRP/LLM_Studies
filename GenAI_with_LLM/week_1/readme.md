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