# HackaQuantum2024.2Grupo3

OBS: O projeto foi desenvolvido em um ambiente de desenvolvimento integrado com o GitHub, utilizando o Visual Studio Code e o Python 3.9.7.
Contudo, alguns aquivos foram criados no Google Colab, para facilitar a execução de alguns códigos. (ex: Quanti.ipynb)
Recomendamos que o projeto seja executado no Google Colab, para evitar possíveis erros de execução.
Segue recomendações sobre como organizar as pastas dos dados:


Dados Qualitativos
Para a realização do trabalho foi usado a biblioteca pandas. Nos arquivos diários, feita a importação dos arquivos .csv, foi realizada a concatenação de todos os arquivos.
Na concatenação, foi verificado a existência de dados vazios na coluna ISIN. As linhas com essa coluna vazia foram retirados da análise, pois não faz sentido computar mudanças de fundos desconhecidos.
Em seguida, para cada coluna foi criado um DataFrame com o ISIN, o campo e a data referente ao campo, além de ter sido ordenado em relação ao fundo e a data. Existem os DataFrames contendo os campos obrigatórios e em outra célula com os demais. Como rodar todos fez estourar a memória, vamos focar nos campos principais. De modo a computar as mudanças, primeiramente, criamos um novo DataFrame com as colunas ["ISIN","data_valor_antigo","data_valor_novo","campo","valor antigo","valor novo" ].
Por fim, para registrar as mudanças, focamos na leitura do DataFrame em relação ao campo e depois filtramos por fundo. Após a filtração, a ideia é comparar cada linha com a próxima e verificar se houve mudança no valor. Caso haja mudança no valor, então registraremos no novo DataFrame criado.




