# Mini-Projeto Avaliativo - Módulo 2

**Curso:** Visualização de Dados e Business Intelligence - SCTec  
**Aluna:** Zaira Nanci Zatelli Wendt  
**Turma:** Turma 2  
**Projeto:** Dashboard de Compras de Medicamentos e Dispositivos Médicos - BPS  
**Período analisado:** 2020 a 2026  
**Ferramenta principal:** Power BI  

# Análise das Compras de Medicamentos e Dispositivos Médicos - BPS

## Sobre o projeto

Este projeto foi desenvolvido como parte do Mini-Projeto Avaliativo do Módulo 2 do curso de Visualização de Dados e Business Intelligence - SCTec.

O objetivo é desenvolver um dashboard para analisar as compras de medicamentos e dispositivos médicos registradas no Banco de Preços em Saúde (BPS) entre os anos de 2020 e 2026.

A análise busca facilitar a visualização dos dados e permitir a comparação de valores, quantidades, instituições compradoras, fornecedores, produtos e modalidades de compra ao longo do período.

## Contexto

O Banco de Preços em Saúde reúne informações sobre compras de medicamentos e dispositivos médicos realizadas por instituições públicas e privadas.

Devido à quantidade de informações disponíveis, o uso de ferramentas de Business Intelligence pode ajudar na organização e análise desses dados, facilitando a identificação de padrões e variações nos registros de compras.

É importante considerar que diferenças de preços encontradas na análise não representam necessariamente economia, sobrepreço ou irregularidade. Essas diferenças podem estar relacionadas a fatores como fabricante, apresentação do produto, unidade de fornecimento, quantidade adquirida, localidade, modalidade de compra e período da negociação.

## Fonte dos dados

Os dados utilizados neste projeto são provenientes do Banco de Preços em Saúde (BPS), disponibilizado pelo Ministério da Saúde no Portal Brasileiro de Dados Abertos.

Foram utilizados os arquivos em formato CSV correspondentes aos anos:

- 2020
- 2021
- 2022
- 2023
- 2024
- 2025
- 2026

Também foi utilizado o dicionário de dados oficial do BPS para auxiliar na compreensão das informações disponíveis na base.

## Ferramentas utilizadas

- Power BI
- Power Query
- Git
- GitHub

## Entendimento inicial dos dados

Inicialmente, foram analisados os arquivos anuais do BPS referentes ao período de 2020 a 2026.

Durante essa etapa, foi verificada a estrutura dos arquivos e as colunas disponíveis em cada ano. Os sete arquivos apresentaram 36 colunas com a mesma nomenclatura, não sendo identificadas diferenças na estrutura das colunas entre os anos.

A quantidade de registros encontrada em cada arquivo foi:

- 2020: 84.919 registros
- 2021: 85.012 registros
- 2022: 89.546 registros
- 2023: 33.809 registros
- 2024: 28.815 registros
- 2025: 34.174 registros
- 2026: 11.090 registros

Apesar de não terem sido encontradas diferenças nos nomes das colunas, os tipos de dados, valores nulos, campos vazios, possíveis duplicidades e outras inconsistências serão avaliados durante a etapa de preparação dos dados. 

## Perguntas de negócio

Para direcionar a construção do dashboard, foram definidas as seguintes perguntas:

1. Como evoluiu o valor total registrado das compras entre 2020 e 2026?
2. Quais estados e municípios apresentam maior volume financeiro de compras?
3. Quais instituições compradoras apresentam maior valor registrado?
4. Quais medicamentos e dispositivos médicos foram mais adquiridos?
5. Quais produtos apresentam maior valor total registrado?
6. Quais fornecedores e fabricantes possuem maior participação nos registros?
7. Como os preços unitários variam ao longo do período analisado?
8. Quais modalidades de compra são mais utilizadas?
9. Existem diferenças relevantes de preços entre produtos comparáveis, considerando fornecedores, instituições e períodos diferentes?

### Verificação dos formatos dos dados

Também foi realizada uma verificação inicial dos principais campos que serão utilizados no dashboard.

Os tipos encontrados foram consistentes entre os arquivos de 2020 a 2026:

- ano_compra: número inteiro
- dt_compra: campo de texto no arquivo original, no formato dia/mês/ano
- qt_medicamento: número inteiro
- vl_preco_unitario: número decimal
- vl_preco_total: número decimal
- Campos de localização, instituições, produtos, fornecedores e modalidades: texto

Durante essa análise inicial, também foram identificados alguns valores ausentes no campo de instituição compradora em determinados anos. Esses casos serão investigados e tratados na etapa de preparação dos dados.

A coluna de data será convertida para o tipo Data durante o tratamento no Power Query.

## Preparação e Tratamento dos Dados

Os dados utilizados no projeto foram disponibilizados em arquivos CSV separados por ano, abrangendo o período de 2020 a 2026.

Para facilitar a análise no Power BI, os arquivos foram importados e combinados utilizando o Power Query, formando uma única base de dados.

Durante essa etapa foram realizados alguns tratamentos para organizar a base e preparar os dados para as análises.

### Tratamentos realizados

- Combinação dos arquivos CSV referentes aos anos de 2020 a 2026.
- Ajuste dos cabeçalhos das colunas.
- Remoção de linhas de cabeçalho que apareceram novamente após a combinação dos arquivos.
- Criação e validação da coluna ano_compra, permitindo identificar o ano correspondente a cada registro.
- Verificação dos valores da coluna de UF (sg_uf).
- Verificação dos valores da coluna de esfera administrativa (ds_esfera), que apresentou as categorias Estadual, Municipal e Privada.
- Ajuste dos tipos de dados das principais colunas utilizadas na análise.
- Conversão das colunas dt_compra e dt_insercao para o tipo Data.
- Ajuste das colunas vl_capacidade, vl_preco_unitario e vl_preco_total para formato numérico.
- Conversão da coluna qt_medicamento para número inteiro, permitindo realizar cálculos relacionados à quantidade de itens adquiridos.
- Verificação da qualidade das colunas por meio do recurso de perfil de dados do Power Query.
- Identificação de valores vazios em alguns campos. Esses registros foram mantidos, pois a ausência de informação em uma coluna não significa necessariamente que o registro da compra seja inválido.
- Remoção de colunas que não seriam necessárias para responder às perguntas definidas para o projeto.

### Colunas removidas

Após a combinação dos arquivos, a base apresentou 37 colunas, incluindo a coluna arquivo_origem, utilizada para identificar o arquivo de origem de cada registro. Após a seleção e remoção das colunas que não seriam utilizadas nas análises, a base passou a conter 30 colunas.

Foram removidas as seguintes colunas:

- validade_compra
- co_grupo
- no_grupo
- co_classe
- no_classe
- nu_processo_compra
- nu_ata

A escolha das colunas mantidas foi realizada considerando as informações necessárias para as análises propostas, como período da compra, localização, instituição, medicamento, fornecedor, fabricante, modalidade da compra, quantidade e valores.

Os valores nulos não foram removidos de forma automática. A decisão foi manter esses registros quando as demais informações da compra permaneciam válidas, evitando a perda desnecessária de dados.

Também foi realizada uma verificação de possíveis duplicidades utilizando a coluna co_seq_bps como referência para identificação dos registros. Na análise realizada não foram identificadas duplicidades na amostra verificada. Por esse motivo, não foi aplicada a remoção automática de registros duplicados, evitando a exclusão de compras que poderiam representar registros válidos.

Após a conclusão dos tratamentos no Power Query, os dados foram carregados para o Power BI para dar continuidade à etapa de definição dos indicadores e construção do dashboard. 

### Definição de KPIs e métricas

Após a preparação dos dados, foram criadas medidas no Power BI utilizando DAX para apoiar as análises do dashboard.

Foram definidos os seguintes indicadores:

Valor Total das Compras: soma dos valores totais registrados nas compras.
Quantidade Total: soma das quantidades adquiridas.
Preço Unitário Médio: média dos preços unitários registrados.
Total de Registros: quantidade de registros presentes na base consolidada.
Total de Fornecedores: quantidade distinta de fornecedores, considerando o CNPJ.

As medidas foram testadas individualmente por meio de cartões no Power BI para verificar os resultados antes da construção dos demais visuais.

O preço unitário médio será utilizado apenas como indicador geral. Nas análises de variação de preços, serão considerados também fatores como produto, apresentação, fornecedor, instituição e período, pois diferenças de preço não representam, isoladamente, economia, sobrepreço ou irregularidade.