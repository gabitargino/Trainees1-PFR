# Trainees1-PFR

## Conteúdo
1. [Introdução](#introdução)
2. [Análise Exploratória de Dados](#análise-exploratória-de-dados)
3. [Limpeza de Dados](#limpeza-de-dados)
4. [Conclusão](#conclusão)
5. [Referências](#referências)

## Introdução
O dataframe utilizado neste projeto contém dados coletados de [um estudo realizado entre 1874 e 1884 na Mayo Clinic sobre cirrose biliar primária](https://www.kaggle.com/datasets/aadarshvelu/liver-cirrhosis-stage-classification).

## Análise Exploratória de Dados
Antes de iniciar a limpeza de dados, foram realizadas as seguintes etapas de pré-processamento:
- **Carregamento dos Dados:** Os dados foram carregados a partir do arquivo CSV, obtido do Kaggle.
- **Tradução:** Para melhor compreensão, foi necessária a tradução e simplificação de determinados nomes de colunas do dataframe, além da adição de unidades para tipos numéricos. As traduções resultaram em:
    - `N_Days`: Número de dias até um transplante, morte ou fim do estudo.
    - `Status`: Situação do paciente, se foi transplantado (CL), morreu (D) ou sobreviveu (C).
    - `Drug`: Droga administrada.
    - `Age`: Idade do paciente.
    - `Sex`: Sexo do paciente.
    - `Ascites`: Acúmulo de líquido no abdômen.
    - `Hepatomegaly`: Hepatomegalia.
    - `Spiders`: Telangiectasia, pequenos vasos sanguíneos dilatados.
    - `Edema`: Inchaço.
    - `Bilirubin`: Bilirrubina (mg/dl).
    - `Cholesterol`: Colesterol (mg/dl).
    - `Albumin`: Albumina (gm/dl).
    - `Copper`: Cobre na urina (ug/dia).
    - `Alk_Phos`: Fosfatase Alcalina (U/L), unidades por litro.
    - `SGOT`: Aspartato Aminotransferase (U/L), unidades por litro.
    - `Tryglicerides`: Triglicerídeos (mg/dl).
    - `Platelets`: Plaquetas (ml/1000), número de plaquetas por milímetro cúbico.
    - `Prothrombin`: Tempo de Protrombina (s), segundos.
    - `Stage`: Estágio da cirrose biliar primária.

    Além disso, também houve a substituição de alguns termos:
    - `D-penicillamine`: `D-penicilamina`
    - `Y`: `S`
    - `N`: `N`
    - `C`: `Sobreviveu`
    - `D`: `Morte`
    - `CL`: `Transplante`

- **Retirada de Duplicatas:** Foi feita a verificação da existência de linhas duplicadas e sua filtragem.

- **Criação dos arquivos CSV:** Após o pré-processamento, foram gerados 3 arquivos CSV para diferentes propósitos:
    - `liver_cirrohosis_v1.csv`: Este arquivo contém o conjunto de dados tratado e completo, com todas as colunas.
    - `liver_cirrohosis_v2.csv`: Contém apenas as colunas relacionadas a Sintomas e Estágios, destinado a prever o Estágio da cirrose.
    - `liver_cirrohosis_v3.csv`: Inclui as colunas de Idade, Estágio e Situação, com o objetivo de prever o evento de morte, transplante ou sobrevivência, além dos sintomas relevantes, tais como:
        - `Bilirrubina (mg/dl)`: Pode indicar maior taxa de mortalidade.
        - `Albumina (gm/dl)`: Reflete comprometimento da função hepática.
        - `Aspartato Aminotransferase (U/L)`: Indicador de dano hepático.
        - `Plaquetas (ml/1000)`: Associadas a complicações hepáticas.
        - `Tempo de Protrombina (s)`: Prolongamento indicativo de comprometimento na coagulação sanguínea.

## Conclusão
## Referências
-Marini, S., & Fraga, R. Título da matéria. MedicinaNet, 2014. Disponível em: [https://www.medicinanet.com.br/conteudos/revisoes/5619/cirrose_e_suas_complicacoes.htm].
