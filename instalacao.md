# Instalação

A primeira linha do script deverá ser trocada para a base na qual se deseja alocar as rotinas.

Também será necessário executar as linhas:\
\
`CREATE SCHEMA [DESENV]`\
`GO`\
``\
``Esta linha é necessária, pois todas funções e procedimentos armazenados utilizam este esquema como padrão.\
Utilizar esse esquema facilita encontrar todas as DDL's relativas à rotinas que serem utilizadas somente em desenvolvimento, mantendo o ambiente organizado e despoluído.
