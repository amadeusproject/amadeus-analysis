# Objetivo
O objetivo deste documento é explicar como extrair o schema do banco do Amadeus LMS utilizando a ferramenta schemaspy (http://schemaspy.org/)




## Conhecimentos necessários

1. Java básico
2. Terminal
3. Postgres/banco de dados
4. Inglês básico


# 1. Baixar os arquivos necessários

Dois arquivos são necessários, primeiro o .jar do schemaspy que está disponível na página: https://github.com/schemaspy/schemaspy/releases

E outro, em específico para o Amadeus LMS que utiliza o postgresql como banco de dados, é o .jar contendo um JDBC driver de conexão para o mesmo, o jar para o postgres pode ser baixado na página: https://jdbc.postgresql.org/download.html


# 2. Conseguir as credenciais
Em algum momento, você setou as credenciais do seu banco do amadeus, provavelmente estão localizadas em variáveis de ambiente ou no arquivo local_settings.py .

# 3. executar o comando
Como descrito na documentação do schemaspy (), para o postgres só necessitamos destes campos:
1. host (host onde o postgres está localizado)
2. port (porta do host que o psotgres escuta)
3. db (nome do schema dentro do postgres)
4. dp ( caminho para o driver jdbc do postgresql)
5. t ( tipo de banco, para o postgres, o valor é pgsql)
6. u (usuário do banco)
7. p (caso haja uma senha para o usuário, utilizar este parâmetro)



Um exemplo de comando utilizado:
`java -jar schemaspy-6.0.0.jar -t pgsql -u postgres -o test -db postgres -host localhost:5432 --debug -dp postgresql-42.2.5.jar`