# Attention is all you need
Acredito que tenha chegado a hora de ler e **entender** todo esse [paper](https://arxiv.org/abs/1706.03762)





## Introdução
* Modelos anteriores aos Transformers tinham o problema de "esquecer" quando tratavam com sequências extensas (RNN)
* LSTM surgem para resolver esse problema, porém tendem a demorar pra ajustar

## Transformers
* Depende unicamente do **mecanismo de atenção**, não tem recorrência, portanto tendem a ser mais rápidas para treinar
* O mecanismo de atenção "força" o modelo a dar enfoque em termos mais importantes na sentença

### Arquitetura

* **Encoder**: Constituidos de duas partes: Multi-head Attention e Feed Forward
  * As palavras são recebidas de forma paralela pelo Multi-Head Attention, mas passa pela feed forward de forma separada 
* **Decoder**: Masked Multi-Head Attention, Multi-head Attention e Feed Forward

## Referências

[Transformers for beginners | What are they and how do they work](https://www.youtube.com/watch?v=_UVfwBqcnbM&ab_channel=AssemblyAI)

[The Transformer neural network architecture EXPLAINED. “Attention is all you need”](https://www.youtube.com/watch?v=FWFA4DGuzSc&list=PLpZBeKTZRGPNdymdEsSSSod5YQ3Vu0sKY&index=1&ab_channel=AICoffeeBreakwithLetitia)

[Transformer Neural Networks - EXPLAINED! (Attention is all you need)](https://www.youtube.com/watch?v=TQQlZhbC5ps&t=2s&ab_channel=CodeEmporium)

[The Illustrated Transformer](http://jalammar.github.io/illustrated-transformer/)

[Attention is all you need; Attentional Neural Network Models](https://www.youtube.com/watch?v=rBCqOTEfxvg&ab_channel=PiSchool)

[https://www.datacamp.com/tutorial/building-a-transformer-with-py-torch](https://www.datacamp.com/tutorial/building-a-transformer-with-py-torch)