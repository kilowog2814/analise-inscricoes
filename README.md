# Analise de inscriçoes realizadas entre 2016 - 2023
## Por motivos de segurança da informaçao, as bases de inscriçoes dos anos nao serao divulgadas e alguns itens foram anomizados, como informaçoes de endereço, cursos e identificaçao dos clientes.

### Origem dos dados e Estrtura das bases
Todas as bases foram geradas entre 2016 até 2023.
Todos os dados foram coletados via Forms do Google e salvo em planilhas no Google Drive. Cada nova abertura de turma gera um novo arquivo (no geral temos 4 turmas por ano) e cada turma tem o sua aba propria na planilha.

Os dados sao preenchidos pelos proprios alunos(as) no processo de inscriçao do curso.

Problemas encontrados essa estrutura:
1. Validaçao de dados: muitos dados incompletos ou faltando.
2. Falta de alguns informaçoes mais completas para geraçao de insights: sexo, idade, faixa de renda etc.
3. Falta de um estrutura unificada em um unico lugar.

### Todo o processo de analisa passou pelas etapas de:
1. Coleta de metadados de todos os arquivos
2. Unificaçao de todas as bases em um unico arquivo
3. Enriquecimento dos dados de endereço, considerando os CEPs validos, feito pelo [Brasil API](https://brasilapi.com.br)
4. Analise dos dados gerados.
5. Sugestoes de melhorias.

### Coleta dos Metadados [Notebook](https://github.com/kilowog2814/analise-inscricoes/blob/master/metadados.ipynb)
Esse processo consiste em abrir dados os arquivos nas pastas, pegar as informaçoes de colunas, turma (nome da aba), idioma e nome do arquivo.

Depois de todo esse processo de extraçao, os dados sao unificados em um unico dataframe e esse dataframe é salvo em um arquivo Excel chamado metadados.

### Unificaçao de todas as bases [Notebook](https://github.com/kilowog2814/analise-inscricoes/blob/master/unificarArquivos.ipynb)
Este script desempenha a função de consolidar diversos arquivos, levando em consideração os metadados

### Enriquecimento dos dados de endereço [Notebook](https://github.com/kilowog2814/analise-inscricoes/blob/master/pegarDadosCep.ipynb)
Script que usando a API Brasil, filtros os CEP's validados para pesquisa de dados de endereço.

Para a analise só utilizei os dados macros, UF, Cidade e Bairro.

### Analise dos dados gerados [Notebook]() | [Arquivo pdf]()
Analise dos dados consolidados, respondendo as seguintes perguntas

1. Taxa de conversão inscritos x p agantes
2. Taxa de retenção de alunos de um semestre/ano para o outro
3. De onde vem as inscrições
4. Gráfico mostrando evolução nas inscrições e matrículas ao longo dos anos
5. Reunir todas as informações em um mesmo lugar, para acessarmos com mais facilidade 

No final do arquivo temos uma espaço para sugestões de melhorias
