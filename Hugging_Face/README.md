# Hugging Face NLP Course
* A função `pipeline` retorna um objeto que performa um task end-to-end de NLP (preprocessing, passing the inputs to the model, postprocessing)
* `zero-shot-classification` permite selecionar os labels para classificar
* `fill-mask`vai predizer palavras faltantes de uma sentença

* Geralmente os transformers podem ser dividos em três categorias:

* GPT-like (Transformers autoregressivos)
* BERT-like (Trasnformers autoencoders)
* BART/T5-like(Transformers sequence to sequence)

* **Causal Language Modeling**: Modelos que predizem a próxima palavra já tendo "lido" as n anteriores.
* **Masked Language Modeling**: Modelos que predizem uma palavra mascarada em uma sentença

| Model           | Examples                                   | Tasks                                                                            |
|-----------------|--------------------------------------------|----------------------------------------------------------------------------------|
| Encoder         | ALBERT, BERT, DistilBERT, ELECTRA, RoBERTa | Sentence classification, named entity recognition, extractive question answering |
| Decoder         | CTRL, GPT, GPT-2, Transformer XL           | Text generation                                                                  |
| Encoder-decoder | BART, T5, Marian, mBART                    | Summarization, translation, generative question answering                        |


## Tokenizers and Models
* pytorch_model.bin guarda o dicionário dos pesos.
* *vocabulary*: total de tokens difererntes no corpus
* *padding token*: adicionado para garantir mesmo tamanho das sentenças, pode ser encontrado em `tokenizer.pad_token_id`, note que os tokens de `padding` devem ser mascarados no mecanismo de atenção