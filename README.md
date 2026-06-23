# 📝 README - Coffee Bean Classifier

## Como utilizar este Notebook
1.  **Preparação do Dataset:** Certifique-se de que suas imagens estão organizadas em subpastas dentro do Google Drive (ex: `.../Dataset/Classe_A`, `.../Dataset/Classe_B`).
2.  **Caminho dos Dados:** Altere a variável `CAMINHO_DATASET` na célula de execução para apontar para a sua pasta no Drive.
3.  **Execução:** Execute as células em ordem. O código irá:
    *   Redimensionar as imagens para 224x224.
    *   Extrair 14 características (9 de cor + 5 de textura).
    *   Normalizar os dados (StandardScaler).
    *   Treinar um modelo Random Forest.
    *   Exibir métricas de Acurácia, Precisão, Recall e F1-Score.

## Requisitos
*   `opencv-python`
*   `scikit-image`
*   `scikit-learn`
*   `numpy` / `scipy`

## Explicação Técnica do Projeto

Este projeto implementa um classificador de grãos de café utilizando uma abordagem de **Aprendizado de Máquina Clássico**. Ao contrário de redes neurais profundas, aqui extraí características específicas (manuais) para treinar um modelo.

### O Extrator Híbrido
O coração deste código está na função `extrair_descritor_hibrido`, que combina dois domínios:

1.  **Espaço de Cor HSV:** Extraímos média, desvio padrão e assimetria (*skewness*) dos canais de Matiz (H), Saturação (S) e Valor (V). O HSV é mais robusto a variações de iluminação do que o RGB.
2.  **Textura GLCM (Matriz de Coocorrência de Níveis de Cinza):** Analisamos a relação espacial dos pixels para extrair propriedades como Contraste, Dissimilaridade, Homogeneidade, Energia e Correlação. Isso ajuda a identificar se o grão está liso, rugoso ou danificado.

### O Classificador
Foi utilizado o **Random Forest**, um algoritmo de florestas de decisão que lida muito bem com vetores de características tabulares (neste caso, 14 atributos por imagem) e é resistente a *overfitting*.
