# Projeto de Detecção de Consumo Excessivo de Álcool em Roteiros de Bares

## Visão Geral

Este projeto tem como objetivo desenvolver um modelo de aprendizado de máquina para a detecção de episódios de consumo excessivo de álcool durante roteiros de bares universitários. O conjunto de dados inclui informações de acelerômetros e conteúdo alcoólico transdérmico (TAC) coletados durante eventos de roteiros de bares. O foco principal é prever e identificar momentos de consumo excessivo de álcool, utilizando dados móveis e informações de TAC.

## Destaques do Projeto

- Utilizou-se uma combinação de técnicas de processamento de dados e algoritmos de aprendizado de máquina para construir e avaliar os modelos de detecção de consumo excessivo de álcool.
- Dado o foco na identificação precisa, optou-se pelo uso de modelos de classificação e regressão.
- Alcançou-se uma média de TAC de 0,065 +/- 0,182 e uma máxima de 0,443, com quartis internos de 0,002, 0,029 e 0,092.
- O tempo médio até a última ingestão de bebida foi calculado como 16,1 +/- 6,9 horas.

## Conjunto de Dados

Este projeto utilizou um conjunto de dados obtido do estudo "[Bar Crawl: Detecting Heavy Drinking](https://doi.org/10.24432/C5TK6G)", que contém dados de acelerômetros e TAC coletados durante roteiros de bares universitários. O conjunto de dados consiste em registros de acelerômetros e leituras de TAC em intervalos de tempo, representando diferentes participantes e momentos durante os eventos.

## Informações sobre o Conjunto de Dados

### Informações Relevantes

- Todos os dados presentes no conjunto foram totalmente anonimizados.
- Inicialmente coletados de 19 participantes, com a exclusão dos dados de TAC de 6 participantes devido à sua inutilização.
- Foram considerados os dados de acelerômetros de 13 participantes restantes.
- Dados de acelerômetros foram coletados a partir de smartphones com uma taxa de amostragem de 40Hz.
- Dados de TAC foram obtidos através de pulseiras de tornozelo SCRAM em intervalos de 30 minutos.

### *Bar Crawl*

![Bar Crawl](https://www.chicagomag.com/wp-content/archive/Chicago-Magazine/December-2018/A-Celebration-of-Winter/Go-on-the-Ultimate-Indoor-Bar-Crawl/map2.png)

A *bar crawl* é um evento em que os participantes visitam vários bares ou pubs em uma única noite, consumindo bebidas alcoólicas em cada local. Na universidade, esse evento é uma atividade social muitas vezes organizada por grupos de estudantes ou como parte de eventos no campus. Esses roteiros proporcionam aos estudantes a oportunidade de socializar, comemorar e experimentar a vida noturna local.

Durante um roteiro de bares, os participantes podem consumir quantidades variáveis de álcool, e momentos de consumo excessivo podem ocorrer. O objetivo deste projeto é prever esses momentos de consumo excessivo, analisando dados de acelerômetros de smartphones e informações de TAC coletadas por meio de pulseiras de tornozelo SCRAM.

### Dados de Acelerômetros

Os dados de acelerômetros foram coletados de uma variedade de smartphones, incluindo iPhones e Androids. O arquivo de dados "all_accelerometer_data_pids_13.csv" contém informações de tempo, ID do participante e amostras de cada eixo do acelerômetro (x, y, z).

### Dados de TAC

As leituras de TAC estão disponíveis em dois diretórios: "raw_tac" e "clean_tac". O diretório "raw_tac" contém as leituras de TAC não processadas, enquanto o diretório "clean_tac" contém leituras de TAC processadas. As leituras de TAC processadas incluem informações de tempo e leituras de TAC, com ajustes para melhor alinhar os dados.

### Tipos de Smartphones

O arquivo "phone_types.csv" fornece informações sobre os tipos de smartphones usados durante a coleta de dados. Ele inclui a correspondência entre o ID do participante e o tipo de smartphone (iPhone ou Android).

### Informações Adicionais

Para obter detalhes completos sobre o processamento dos dados, consulte o estudo referenciado: [The determination of blood alcohol concentration by transdermal measurement](https://www.scramsystems.com/images/uploads/general/research/the-determination-of-blood-alcohol-concentrationby-transdermal-measurement.pdf) por J. Robert Zettl (2002).

## Informações sobre Atributos

### Principais Atributos

1. `all_accelerometer_data_pids_13.csv`:
   - `time`: Inteiro, carimbo de data/hora Unix em milissegundos.
   - `pid`: Simbólico, ID do participante das 13 categorias listadas em `pids.txt`.
   - `x`: Contínuo, dados de séries temporais do eixo x do acelerômetro.
   - `y`: Contínuo, dados de séries temporais do eixo y do acelerômetro.
   - `z`: Contínuo, dados de séries temporais do eixo z do acelerômetro.

2. `clean_tac/*.csv`:
   - `timestamp`: Inteiro, carimbo de data/hora Unix em segundos.
   - `TAC_Reading`: Contínuo, dados de séries temporais do conteúdo alcoólico transdérmico.

3. `phone_types.csv`:
   - `pid`: Simbólico, ID do participante das 13 categorias listadas em `pids.txt`.
   - `phonetype`: Simbólico, tipo de smartphone (iPhone ou Android).

### Outros Atributos

Atributos adicionais podem ser encontrados no diretório `raw`, em formato de arquivos Excel. Eles incluem informações sobre o nível de TAC, voltagem infravermelha, temperatura, data e hora.

## Distribuição do Alvo

A variável alvo, TAC (Conteúdo Alcoólico Transdérmico), é medida em g/dl, onde 0,08 é o limite legal para intoxicação ao dirigir.
- Média de TAC: 0,065 +/- 0,182
- Máximo TAC: 0,443
- Quartis Internos do TAC: 0,002, 0,029, 0,092
- Média de Tempo até a Última Bebida: 

