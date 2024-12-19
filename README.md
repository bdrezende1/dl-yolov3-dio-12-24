# dl-yolov3-dio-12-24
Vamos rotular uma base de dados e aplicar o treinamento com a rede YOLO.
---
# YOLOv3 Training Guide Using Google Colab and Darknet

Este notebook do Google Colab permite treinar o modelo YOLOv3 usando o framework Darknet. Abaixo está um guia detalhado das principais seções e funcionalidades.

## 1. Configuração Inicial

- O notebook começa configurando o ambiente para usar GPU no Google Colab
- Conecta o Google Drive para armazenar e acessar arquivos
- Cria uma pasta "darknet" no Google Drive que será sincronizada com o computador local
- Usa o comando `drive.mount()` para montar o Google Drive no ambiente Colab

## 2. Verificação e Instalação de Dependências

- Verifica a versão do CUDA instalada no ambiente 
- Instala o cuDNN (biblioteca de deep learning da NVIDIA) compatível com a versão do CUDA
- O cuDNN precisa ser baixado manualmente do site da NVIDIA e colocado na pasta do projeto
- Os arquivos são descompactados e instalados no sistema

## 3. Instalação do Darknet

- Clona um fork modificado do repositório Darknet (baseado no repo do AlexeyAB)
- As modificações permitem trabalhar com espaços nos caminhos do Drive e reduzem logs
- Compila o Darknet na primeira execução
- Nas execuções seguintes, usa uma versão compilada salva no Drive para economizar tempo

## 4. Funções Utilitárias

- `imShow()`: Função para exibir imagens no notebook
- `upload()`: Permite fazer upload de arquivos para o ambiente
- `download()`: Permite baixar arquivos do ambiente

## 5. Preparação para Treinamento

- Explica a estrutura de arquivos necessária (obj.data, yolov3.cfg, etc)
- Oferece 3 opções para carregar o dataset:
  1. Usar direto do Drive
  2. Copiar para o filesystem local do Colab
  3. Clonar de um repositório git

## 6. Treinamento

- Executa o treinamento usando o comando darknet detector train
- Salva backups dos pesos a cada 100 iterações
- Permite retomar o treinamento de onde parou usando os últimos pesos salvos

## Principais Características

- Usa GPU do Colab (12GB RAM)
- Sincroniza com Google Drive para persistência
- Otimizado para reiniciar rapidamente após quedas
- Salva backups que são sincronizados automaticamente
- Inclui várias otimizações para trabalhar com as limitações do Colab

---

O código fornece uma estrutura completa para treinar modelos YOLOv3 no ambiente gratuito do Google Colab, lidando com as principais limitações da plataforma.
