<h1>Processamento de Números de Processos Judiciais.</h1>>

Este projeto processa números de processos judiciais a partir de um arquivo Excel, formata os números, verifica a validade e salva os dados processados em um novo arquivo Excel.

Requisitos:
. Python 3.x
. Pandas
. re (Regular Expressions)
. logging

Funcionalidades:
. Formatação de números de processos judiciais para 20 caracteres. . Verificação de números vazios ou contendo apenas zeros. . Verificação e classificação de números de processos como NUP (Número Único de Processo) ou Correspondência. . Leitura de dados de um arquivo Excel. . Salvamento de dados processados em um arquivo Excel com múltiplas planilhas. . Filtragem e organização dos dados processados. Dependências: . pandas . re

Função "formatar_numero_processo(numero)":
Formatação de Número de Processo Formata um número de processo removendo todos os caracteres não numéricos e ajustando o tamanho para 20 caracteres com preenchimento à esquerda com zeros, se necessário.

Parâmetros:

numero (str): O número do processo judicial.

Retorna:

(str): O número do processo formatado ou uma string vazia se o número não for válido. Log: . Emite um INFO se o número tem menos de 18 caracteres. . Emite um INFO se o número tem mais de 20 caracteres.

Função "verificar_vazio_ou_zeros(numero_formatado)":

Verifica se o número formatado está vazio ou contém apenas zeros.

Parâmetros:

numero_formatado (str): O número do processo formatado.

Retorna:

(bool): True se o número estiver vazio ou contiver apenas zeros, caso contrário, False.

Função "verifica_nup_jud(numero_formatado)":

Verifica se o número formatado é um NUP válido ou uma correspondência. Parâmetros:

numero_formatado (str): O número do processo formatado.

Retorna:

(str): 'NUP' se for um NUP válido, 'Correspondencia' se for uma correspondência, 'Invalido' se for inválido.

Regras: . Verifica segmentos de data válidos (1950-2025). . Usa regex para verificar padrões específicos de NUP.

Função "ler_excel(arquivo_entrada)":

Lê o arquivo Excel de entrada e retorna um DataFrame.

Parâmetros:

arquivo_entrada (str): O caminho para o arquivo Excel de entrada.

Retorna:

(DataFrame): O DataFrame com os dados do arquivo Excel, ou None em caso de erro.

Função "salvar_excel(dfs, arquivo_saida)":

Salva os DataFrames em um arquivo Excel com múltiplas planilhas, separando e renomeando as colunas desejadas.

Parâmetros:

dfs (dict): Dicionário de DataFrames a serem salvos, onde as chaves são os nomes das planilhas.

arquivo_saida (str): O caminho para o arquivo Excel de saída.

Retorna:

None

Função "processar_dados_excel(arquivo_entrada)":

Processa o arquivo Excel de entrada e retorna DataFrames processados.

Parâmetros:

arquivo_entrada (str): O caminho para o arquivo Excel de entrada.

Retorna:

(dict): Um dicionário com os DataFrames processados: 'Processos Válidos': DataFrame com os processos válidos. 'NUP': DataFrame com os processos NUP. 'Processos Inválidos': DataFrame com os processos inválidos. None em caso de erro.

Contribuição:

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

Licença:

Este projeto está licenciado sob a MIT License.
