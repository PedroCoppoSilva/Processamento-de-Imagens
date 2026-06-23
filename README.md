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
