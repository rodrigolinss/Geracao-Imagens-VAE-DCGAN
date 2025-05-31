# Geração de Imagens de Olhos com VAE e DCGAN

Este projeto explora a geração de imagens sintéticas de olhos utilizando duas abordagens populares de Deep Learning: Variational Autoencoder (VAE) e Deep Convolutional Generative Adversarial Network (DCGAN).

## Objetivo

O objetivo principal é treinar modelos capazes de aprender as características de um dataset de imagens de olhos e gerar novas imagens realistas que se assemelhem às originais.

## Modelos Utilizados

1.  **Variational Autoencoder (VAE):** Um modelo generativo que aprende uma representação latente (codificada) dos dados e a utiliza para reconstruir e gerar novas amostras. Tende a produzir imagens mais suaves e com boa cobertura da distribuição dos dados, mas pode apresentar borramento.
2.  **Deep Convolutional GAN (DCGAN):** Uma rede adversária composta por um Gerador e um Discriminador que competem entre si. O Gerador tenta criar imagens falsas realistas, enquanto o Discriminador tenta distinguir as imagens reais das falsas. Geralmente produz imagens mais nítidas e com maior potencial de realismo, mas pode sofrer de instabilidade no treinamento e gerar artefatos.

Ambos os modelos utilizam Redes Neurais Convolucionais (CNNs) para processamento eficiente das imagens.

## Dataset

O projeto foi desenvolvido utilizando um dataset de imagens de olhos. O notebook está configurado para ler imagens de um diretório específico (originalmente `/kaggle/input/eye-detection-dataset/Dataset/test/images`, mas pode ser adaptado).

## Resultados Obtidos

Ao final da execução, o notebook apresenta:

* Gráficos de perda para VAE e GAN durante o treinamento.
* Exemplos de imagens de olhos geradas por ambos os modelos.
* Uma comparação visual lado a lado dos resultados do VAE e da GAN.
* Um teste da capacidade do Discriminador da GAN em diferenciar imagens reais e falsas, com métricas quantitativas.

### Gráficos de Perda

Os gráficos de perda mostram o comportamento dos modelos durante o treinamento.

* **VAE:** O gráfico demonstra uma queda suave na perda ao longo das épocas, indicando convergência e aprendizado gradual.
* **GAN:** O gráfico exibe flutuações nas perdas do Gerador e do Discriminador, o que é típico do treinamento adversarial. Observa-se que a perda do Discriminador permanece relativamente baixa, enquanto a do Gerador varia mais.

### Resultados da Geração de Imagens

* **VAE (150 Épocas):** As imagens geradas pelo VAE apresentam um aspecto mais borrado e cores menos vibrantes, mas mantêm uma forma geral reconhecível de olhos.
* **DCGAN (150 Épocas):** As imagens geradas pela DCGAN exibem maior nitidez e detalhes mais definidos, como íris e pestanas, mas também mostram mais variações e artefatos, como cores distorcidas ou formas irregulares.

### Comparação

A comparação visual destaca as diferenças entre as abordagens. O VAE, com sua abordagem de codificação e decodificação, gera imagens mais consistentes em termos de estrutura, mas com menos detalhes. A GAN, por sua vez, busca o realismo através da competição, resultando em imagens mais detalhadas, mas também mais suscetíveis a imperfeições.

### Teste do Discriminador

O teste do Discriminador fornece uma avaliação quantitativa da capacidade do modelo em distinguir imagens reais e falsas.

* **Pontuação média para imagens REAIS:** 0.6486
* **Pontuação média para imagens FALSAS:** 0.0558
* **Diferença média:** 0.5927

A alta diferença média (0.5927) indica que o Discriminador ainda consegue diferenciar bem as imagens geradas pela GAN das reais, sugerindo que o Gerador ainda precisa ser aprimorado para produzir imagens mais convincentes. As pontuações individuais mostram que algumas imagens reais são classificadas com pontuações mais baixas do que o ideal, enquanto as falsas recebem pontuações muito baixas.
