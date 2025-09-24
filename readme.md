# Problema de Regressão

## Disciplina
Projetos de Sistemas Baseados em Aprendizado de Máquina

## Componentes
Paula de Souza Braz <br/>
Ítalo Maciel de Paiva

## Descrição
Este projeto tem como objetivo aplicar os conhecimentos obtidos na 1ª unidade da disciplina no problema de classificação de preços de residências airbnb.

## Objetivos
- Melhorar o EDA e seleção/criação de features;
- Diferentes formas de normalização (e.g: min-max);
- Modificação do algoritmo de otimização (e.g: adm, nadam, etc);
- Outras estratégias que acharem pertinente mas mantendo o foco na regressão (e.g: LR diferentes, regularização, etc);

## Requisitos
- Uso obrigatório da classe "Architecture" fornecida em sala de aula e do framework PyTorch para o desenvolvimento da "solução melhorada".
- Comparação de desempenho com outras bibliotecas:
1. LazyPredict
2. PyCaret
- Opcional: Interface gráfica usando o gradio.

# Descrição

## Desafios
O principal desafio encontrado foi na transformação de dados categóricos para dados numéricos, houve tentativas em utilizar a função dummies(), que consiste em transformar cada categoria de uma coluna em valores booleanos, contudo essa abordagem não foi adequada por dois motivos:
- Gerou uma quantidade exagerada de novas colunas codificadas quando uma coluna possuía muitas categorias, logo na visualização do dataset tratado impossibilitava validar os dados manualmente.
- Ao aplicar o passo referente a definir os valores extremos para cada categoria tratada, sendo os valores booleanos (0 ou 1), o modelo não conseguia realizar o filtro corretamente, devido que não ocorria uma variação grande de valores e produzia um resultado inadequado na execução do treinamento do modelo.
Foi utilizada o Categorical para codificação de cada valor categórico em uma numeração de forma ordenada. E essa estratégia de tratamento gerou um melhor resultado na aplicação da regressão linear.

## Normalização dos dados
Foram utilizadas três abordagens:
- Min-Max Scaling: A curva apresentava suavização. 
- Z-Score: A curva com um determinado número de épocas, apresentava uma aproximação quase que perfeita.
- Log Transformation: A curva de aprendizado possuía muitos ruídos.

## Otimização
Foram utilizadas três tipos de otimização:
- Gradiente Descendente
- Adam
- RMSProp

## Comparação com a biblioteca LazyPredict
Comparando o desempenho do PyTorch, o LazyPredict teve predições erradas para muitos casos considerados extremos.


