# Importanto-Consulta-SQL-para-Python
Fazendo a imporntação do Banco de dados Postgre para Python 


import psycopg2
import pandas as pd

# Parâmetros de conexão
dbname   = 'python'
user     = 'postgres'
password = 'noah'
host     = 'localhost'
port     = '5435' 

# Criar uma conexão
conexao = psycopg2.connect(dbname=dbname,
                        user=user,
                        password=password,
                        host=host,
                        port=port)


cursor = conexao.cursor() 

query = """
select 
aeronave
,datavalidade
,operador
,tipouso
,modelo

from public.mapeamento """

df=pd.read_sql_query(query,conexao)
df.head(2)
