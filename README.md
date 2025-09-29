# MVP – Machine Learning  
### Especialização em Ciência de Dados e Analytics – PUC-Rio

Este repositório contém o projeto de **Machine Learning aplicado a risco de crédito**, desenvolvido como parte da especialização em **Ciência de Dados e Analytics (PUC-Rio)**.  
O objetivo principal foi construir um **modelo de Probabilidade de Default (PD)**, avaliando diferentes abordagens de pré-processamento e modelagem.

---

## Estrutura do Repositório

- **ml_sprint.ipynb**  
  Notebook principal do projeto, contendo:
  - Explicação detalhada da abordagem adotada.  
  - Pré-processamento dos dados.  
  - Seleção de modelos e otimização de hiperparâmetros.  
  - Treinamento, avaliação e comparação dos fluxos de modelagem.  

- **fluxograma_processo_modelagem.png**  
  Diagrama ilustrando, de forma visual, a lógica e o fluxo do processo de modelagem implementado no notebook.  

- **Versão no Google Colab**  
  O mesmo código presente no notebook também está disponível no Colab para execução direta (fique atento ao ponto de estouro de memória descrito no início do notebook):  
  [Abrir no Google Colab]([https://drive.google.com/file/d/1SeKBVCDJHBv8B5faD0FGRbrTSgcTdptd/view?usp=sharing](https://drive.google.com/file/d/1SeKBVCDJHBv8B5faD0FGRbrTSgcTdptd/view?usp=sharing))

- **Modelos finais treinados**  
  Os modelos resultantes do treinamento também estão salvos no repositório:  
  - `gb_final_sem_fte.joblib` → modelo referente ao **Fluxo A** (pré-processamento simples).  
  - `gb_final_com_fte.joblib` → modelo referente ao **Fluxo B** (processamento robusto com *binning*).  

---

## Objetivo do Projeto

Desenvolver e comparar duas abordagens para a modelagem da **Probabilidade de Default (PD)**:  
- **Fluxo A**: pré-processamento simples seguido por seleção e treinamento de modelos.  
- **Fluxo B**: processamento robusto, incluindo *binning* de variáveis contínuas e rotulagem de faixas, com foco em explicabilidade e redução de impacto de outliers.  

Além disso, os dados foram divididos em:
- **Baseline (2021-05 → 2024-08)**: utilizado para treino e teste durante o desenvolvimento.  
- **Monitoramento (a partir de 2024-08)**: reservado para simular o uso do modelo em produção.  

---

## Resultados

- O **Gradient Boosting** foi o modelo escolhido por apresentar o melhor desempenho em termos de **f1-score**, priorizando a correta identificação de clientes inadimplentes.  
- O **Fluxo B** foi selecionado como versão final do modelo, pois, apesar de ter métricas ligeiramente inferiores ao Fluxo A, apresentou:  
  - Maior **explicabilidade** (importante em auditorias e re-treinamentos).  
  - Redução de aproximadamente **50% no tempo de treinamento**.  

---

## Próximos Passos

- Aplicar **normalização/padronização** em variáveis contínuas antes do *optbinning*.  
- Realizar **análise de correlação** para reduzir redundâncias e aumentar a eficiência do modelo.  
- Explorar **modelos de clustering** para criação de novas variáveis que possam enriquecer a base de treino.  

---

## Observação

Este projeto foi desenvolvido no contexto acadêmico da especialização, mas a abordagem e os conceitos aplicados seguem práticas utilizadas no mercado em **gestão de risco de crédito** e **modelagem de PD**.  
