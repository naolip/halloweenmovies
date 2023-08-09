 # Integração da API de Filmes de Halloween com o Google Sheets 🎃

## Visão Geral

Este é um projeto em Python desenvolvido para obter dados de 13 filmes da franquia Halloween da API OMDb e armazená-los em uma planilha do Google Sheets. Os filmes são especificados pelos seus títulos e anos de lançamento, e as informações obtidas da API incluem detalhes como título, ano, classificação IMDb e outros.

![Texto em Markdown](https://github.com/naolip/halloweenmovies/blob/main/Workflow.png?raw=true)
## Requisitos

Antes de executar o projeto, certifique-se de ter os seguintes requisitos instalados:

- Python 
- Pandas,
- Requests
- gspread 
- oauth2client

## Extração dos Dados

O script utiliza a função `movies(key, query_title, year)` para buscar os dados dos filmes na API OMDb. A função recebe a chave da API OMDb, uma lista de títulos de filmes (`query_title`) e uma lista correspondente de anos de lançamento (`year`). Em seguida, a função percorre os títulos e anos de lançamento dos filmes, envia uma solicitação para a API OMDb e armazena as informações dos filmes em uma lista de dicionários chamada `movie_info_list`. Por fim, a função retorna um DataFrame do pandas contendo os dados dos filmes.

## Informações dos Filmes

O script coleta as informações dos 13 filmes de Halloween especificados nas listas `query_title` e `year`. Os dados de cada filme são obtidos usando a API OMDb e armazenados como uma linha em um DataFrame do pandas.

## Limpeza e Formatação dos Dados

Script realiza uma limpeza, removendo colunas desnecessárias do DataFrame `dfmovies`.

O DataFrame limpo é armazenado em uma variável chamada `df1`.

## Ordenação e Exportação

O DataFrame `df1` é ordenado com base na classificação IMDb em ordem crescente. Os dados ordenados são salvos em um arquivo Excel chamado `movies.xlsx`.

## Integração com o Google Sheets

O script utiliza a API do Google Sheets para autenticação e criação de uma nova planilha com o nome "Halloween Movies". O conteúdo do arquivo `movies.xlsx` é lido em um DataFrame do pandas (`df1`). A primeira guia da nova planilha "Halloween Movies" é obtida, e os dados de `df1` são enviados para essa guia.

## Como Utilizar

1. Configure o arquivo `config.ini` com a sua chave da API OMDb.

2. Certifique-se de ter todas as bibliotecas necessárias instaladas.

3. Execute o script em um ambiente Python.

  
5. Uma nova planilha do Google Sheets chamada "Halloween Movies" será criada, e os dados de `movies.xlsx` serão enviados para a primeira guia.

[planilha](https://docs.google.com/spreadsheets/d/11U6F3pU8TdOHEXhaBRWZVcR7oBP089Jhnt2khrijlBw/edit?usp=drivesdk)

