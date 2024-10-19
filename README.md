# HackaQuantum2024.2Grupo3

Linguagem: Python  

Bibliotecas Necessárias:
- Pandas
- SQLAlchemy
- Dask
- Matplotlib
  
OBS: O projeto foi desenvolvido em um ambiente de desenvolvimento integrado com o GitHub, utilizando o Visual Studio Code e o Python 3.9.7.  
Contudo, alguns aquivos foram criados no Google Colab, para facilitar a execução de alguns códigos. (ex: Quanti.ipynb)  
Recomendamos que o projeto seja executado no Google Colab, para evitar possíveis erros de execução.  
Segue recomendações sobre como organizar as pastas dos dados:  


**Dados Quantitativos:**  
Nos arquivos diários, feita a importação dos arquivos .csv, foi realizada a concatenação de todos os arquivos.  
Na concatenação, foi verificado a existência de dados vazios na coluna ISIN. As linhas com essa coluna vazia foram retirados da análise, pois não faz sentido computar mudanças de fundos desconhecidos.  
Em seguida, para cada coluna foi criado um DataFrame com o ISIN, o campo e a data referente ao campo, além de ter sido ordenado em relação ao fundo e a data. 
Existem os DataFrames contendo os campos obrigatórios e em outra célula com os demais. Como rodar todos fez estourar a memória, vamos focar nos campos principais.  
De modo a computar as mudanças, primeiramente, criamos dois DataFrames com as colunas ["ISIN","data_valor_antigo","data_valor_novo","campo","valor antigo","valor novo" ], um para representar as mudanças e outro pro histórico de cota.  
Por fim, para registrar as mudanças, focamos na leitura do DataFrame em relação ao campo e depois filtramos por fundo. Após a filtragem, a ideia é comparar cada linha com a próxima e verificar se houve mudança no valor. Caso haja mudança no valor, registramos no novo DataFrame criado.


**Para Executar com todas as colunas, rode todas as células do arquivo QuantiFinal.ipynb. Existe uma célula indicada para não ser executada caso desejem apenas as colunas indicadas no arquivo de texto. S**

**Dados Qualitativos:**
Primeiro é feito a leitura do arquivo dizendo as colunas a serem analisadas  
Depois é feito uma identificação das colunas que servirão de referência para o ativo (ISIN,Citi code e EPT Reference Language)  
Depois os arquivos de dados são lidos em chunks para evitar erros e assim conseguirmos testar pequenos pedaços  
Lemos todos os 30 arquivos (os chunks de cada). Se algum arquivo não for encontrado é passado pro próximo  
Depois é verificado se alguma coluna essencial está ausente, se estiver ele ignora o arquivo  
Os arquivos que passarem da verificação são Ordenados de acordo com as colunas de identificação  
Agrupa os registros pelos identificadores, ordenada os registro pelas datas e compara com o registro anterior, assim é verificado se houve mudança  

**Para Executar com todas as colunas, rode todas as células do arquivo QualiFinal.ipynb.**


**Salvamos os CSVs no banco de dados SQL Server para facilitar futuras buscas e filtros utilizando o SGBD da microsoft. Além de facilitar a integração com o Azure Cloud, que já é utilizado internamente na Quantum**

 


