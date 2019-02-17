# Objetivo
O objetivo deste documento é explicar como extrair o schema do banco do Amadeus LMS utilizando a ferramenta schemaspy (http://schemaspy.org/)




## Conhecimentos necessários

1. Java básico
2. Terminal
3. Postgres/banco de dados
4. Inglês básico


# 1. Baixar os arquivos necessários

Dois arquivos são necessários, primeiro o .jar do schemaspy que está disponível na página:

E outro, em específico para o Amadeus LMS que utiliza o postgresql como banco de dados, é o .jar contendo um JDBC driver de conexão para o mesmo, o jar para o postgres pode ser baixado na página:


# 2. Conseguir as credenciais
Em algum momento, você setou as credenciais do seu banco do amadeus, provavelmente estão localizadas em variáveis de ambiente ou no arquivo local_settings.py .

# 3. executar o comando
Como descrito na documentação do schemaspy (), para o postgres só necessitamos destes campos:


Um exemplo de comando utilizado:
`java -jar schemaspy-6.0.0.jar -t pgsql -u postgres -o test -db postgres -host localhost:5432 --debug -dp postgresql-42.2.5.jar`