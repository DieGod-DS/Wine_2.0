# Classificação de Vinhos
!['capa'](/docs/capaimg.png)

# 1. Descrição
- Este é um projeto que visa compreender dados de componentes de vinhos e criar um algoritmo de aprendizado de máquina capaz de predizer a qualidade (bom ou ruim) de vinhos.
- Primeiro, eu desenvolvi minha análise (EDA) inteira em notebooks. Depois, eu dividi o projeto nos componentes responsivos para ingestão de dados, transformação e treinamento de modelo, seguindo os mesmos passos no notebook. Uma vez feito isso, criei scripts para automatizar o treino e predição dos modelos usando estes componentes. Tudo isso executado com boas práticas de codagem e documentação. Meu objetivo final com este projeto é para colocar em prática meus conhecimentos em ciencia de dados, voltados para análise exploratória e algoritmos de IA, obtidos ao longo dos meus estudos.

# 2. Tecnologias e ferramentas
- As tecnlogias utilizadas foram Python (Pandas, Numpy, Matplotlib, Seaborn, Scikit-Learn), Visual StudioCode e GitHub (desenvolvimento do projeto e versionamento),PowerBi (criação rápida de gráficos para análise), algoritmos de aprendizado de máquina, estatística.

# 3. Problema de negócio
**3.1 Qual o problema de negócio?**
- Faço parte do time de desenvolvimento de vinhos de uma empresa, e para um novo produto da nossa marca precisamos entender melhor como se relacionam os componentes de um bom vinho. Para este problema criaremos um modelo capaz de prever a qualidade de um vinho (1 para vinhos bons e 0 para ruins), e com base neste modelo poderemos testar e ter uma prévia da aceitação do público sobre o produto.

**3.2 Qual o contexto?**
- Para nossa empresa é vantajoso testar diferentes combinações de componentes para gerar um vinho com qualidade boa, antes do processo de fabricação.

**3.3 Qual o objetivo do projeto?**
- Ter o máximo de precisão ao classificar um vinho como bom.
- Testar modelos que mais de adequem aos dados.

**3.4 Quais são os benefícios?**
- A empresa reduz o risco de criar um produto com baixa aceitação.
- Reduz prejuízos financeiros.
- É capaz de testar varias combinações de componentes.

# 4. Princpais insights de negócio
1. A porcentagem de bons vinhos nos dados é de aproximadamente 19%
!['winepercent'](/docs//percent_quality.png)

2. Os vinhos foram rotulados com notas de 1 a 10, e para selecionar os vinhos bons eu os categorizei como sendo nota 7 ou superior.
Vinhos bons apresentam um equilibrio entre acidez, taninos, álcool e doçura, arem do aroma característico.
A qualiudade do vinho também está relacionada a sua procedência, safra e as técnicas de vinificação.

3. Abaixo podemos ver a distribuição desse componentes:
!['dist_comp](/docs/data_dist1.png)
Além do desbalanço entre as classes da variável alvo (qualidade), notamos também que a maioria dos componentes não apresentam uma distribuição próxima a normal (curva em forma de sino), isso pode afetar a predição do nosso modelo e por conta disso devemos trata-las.

# 5. Modelagem
1. Após a limpeza e pré-processamento dos dados, onde removi outliers, codifiquei dados categóricos em inteiros, normalizei a distribuição, passamos para a etapa de implementação do modelo, onde testamos 4 algoitmos de classificação diferentes: Regressão Logística, SVM (Máquina de Vetores de Suporte), Árvore de Decisão e Redes Neurais Artificiais.
2. Dentre os modelos selecionados, escolhi o que nos retornou o melhor desempenho com base na ROC-AUC score. A acurácia neste projeto com este dados não seria útil pois a classe dos dados alvo estão desbalanceados.
3. Para encontrar os melhores parâmetros para os modelos, eu os treinei com stratfied k-fold cross validation (validação cruzada com kfold estratificado), pois me retornaria uma estimativa de performance mais realista.
4. Após avaliar o desempenho sobre cada modelo, o que mais se destacou neste projeto foi o SVM. Ele apresentou um recal de 63% (que não julgo ser um bom desempenho) para a classe 1 (classe de vinhos bons).
!['metricsvm'](/docs/svm_metrics.png)
Curva ROC do modelo SVM:
!['rocsvm'](/docs/roc_svm.png)

# 6. Conclusão
Apesar de ter seguido todos os passos com rigor do **CRISP-DM**, acredito quem em algum momento comiti alguma falha que impactou negativmente nossos modelos, pois apresentaram métricas muito abaixo das desejadas. Pelo fato de Redes Neurais Artificiais serem um modelo muito mais robusto, eu esperava um desempenho melhor vindo dele, mas mesmo os outros modelos não atingiram minhas espectativas. Devido aos fatos, buscarei identificar os erros e adquirir conhecimento para soluciona-los, e posteriormente apresentar melhores resultados.