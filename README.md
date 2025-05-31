# Geração de Imagens de Olhos com VAE e DCGAN

Este projeto explora a geração de imagens sintéticas de olhos utilizando duas abordagens populares de Deep Learning: Variational Autoencoder (VAE) e Deep Convolutional Generative Adversarial Network (DCGAN).

## Objetivo

O objetivo principal é treinar modelos capazes de aprender as características de um dataset de imagens de olhos e gerar novas imagens realistas que se assemelhem às originais.

## Modelos Utilizados

1.  **Variational Autoencoder (VAE):** Um modelo generativo que aprende uma representação latente (codificada) dos dados e a utiliza para reconstruir e gerar novas amostras. Tende a produzir imagens mais suaves, mas com boa cobertura da distribuição dos dados.
2.  **Deep Convolutional GAN (DCGAN):** Uma rede adversária composta por um Gerador e um Discriminador que competem entre si. O Gerador tenta criar imagens falsas realistas, enquanto o Discriminador tenta distinguir as imagens reais das falsas. Geralmente produz imagens mais nítidas, mas pode sofrer de instabilidade no treinamento.

Ambos os modelos utilizam Redes Neurais Convolucionais (CNNs) para processamento eficiente das imagens.

## Dataset

O projeto foi desenvolvido utilizando um dataset de imagens de olhos. O notebook está configurado para ler imagens de um diretório específico (originalmente `/kaggle/input/eye-detection-dataset/Dataset/test/images`, mas pode ser adaptado).

## Resultados Obtidos

Ao final da execução, o notebook apresenta:

* Gráficos de perda para VAE e GAN.
* Exemplos de imagens de olhos geradas por ambos os modelos.
* Uma comparação visual lado a lado dos resultados.
* Um teste da capacidade do Discriminador da GAN em diferenciar imagens reais e falsas.
