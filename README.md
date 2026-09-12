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