# Processamento de Imagens em Tons de Cinza e Preto e Branco

Este projeto é um programa em Python, projetado para rodar no Google Colab, que realiza o processamento de uma imagem colorida. Ele converte a imagem para **tons de cinza** e, em seguida, para **preto e branco (binária)** sem depender de bibliotecas como OpenCV, utilizando funções personalizadas.

---

## Recursos do Projeto

1. **Conversão para Tons de Cinza**: 
   - Utiliza a fórmula de luminância perceptual para transformar uma imagem colorida em uma versão em tons de cinza.
   - Fórmula aplicada:
     ```
     gray = 0.2989 * R + 0.5870 * G + 0.1140 * B
     ```

2. **Conversão para Preto e Branco (Binária)**:
   - Gera uma imagem binária a partir de uma imagem em tons de cinza.
   - Utiliza um limiar (threshold) ajustável para decidir quais pixels serão brancos ou pretos:
     - Pixels maiores que o limiar tornam-se brancos.
     - Pixels menores ou iguais ao limiar tornam-se pretos.

---

## Como Usar

1. **Abra o Google Colab**.
2. Copie o código para uma célula do notebook.
3. Execute o código e faça o upload de uma imagem no formato desejado.
4. O programa exibirá três imagens:
   - A imagem colorida original.
   - A imagem convertida para tons de cinza.
   - A imagem binária (preto e branco).

---

## Requisitos

- **Python 3.6 ou superior**.
- As seguintes bibliotecas já vêm instaladas no Google Colab:
  - `PIL` (Pillow)
  - `numpy`
  - `matplotlib`

---

## Estrutura do Código

### 1. Função `to_grayscale`
Responsável por converter uma imagem colorida em tons de cinza.  
- **Entrada**: Imagem colorida (`PIL.Image`).  
- **Saída**: Imagem em tons de cinza (`PIL.Image`).

### 2. Função `to_binary`
Transforma uma imagem em tons de cinza em uma versão binária (preto e branco).  
- **Entrada**: Imagem em tons de cinza (`PIL.Image`) e limiar (padrão: `127`).  
- **Saída**: Imagem binária (`PIL.Image`).

---

## Exemplo de Uso

### Entrada
Uma imagem colorida no formato `.png`, `.jpg`, ou outro compatível.

### Saídas
1. **Imagem Colorida**: Mostra a imagem original carregada pelo usuário.
2. **Imagem em Tons de Cinza**: Uma versão em escala de cinza da imagem original.
3. **Imagem Binária**: Uma imagem onde os pixels são apenas preto ou branco, com base no limiar definido.

---

## Personalização

- **Limiar para binarização**:
  - O valor do limiar pode ser ajustado na função `to_binary`. Por padrão, é `127`, mas você pode alterá-lo para valores entre `0` e `255` para resultados diferentes.
  
  ```python
  binary_image = to_binary(grayscale_image, threshold=150)
