Este pacote contém o código e os recursos necessários para reproduzir as análises estatísticas e visualizações apresentadas no artigo "Cirurgias bariátricas no Sistema Único de Saúde: estudo ecológico de série temporal, 2016-2025.
".  
Estrutura de Arquivos

    analise.ipynb: Script principal em Python que executa todas as etapas da análise (processamento de dados, testes estatísticos e geração de resultados).  
    data/: Pasta com os dados brutos do SUS.  
    logs/: Logs de execução
    BR_UF_2022/: Mapas do brasil em shapefile
    
    resultados_analise_bariatrica: Diretório onde são salvos automaticamente:  
        dados_processados/: Dados que foram processados para analise
        tabelas/: Tabelas em formato Excel (.xlsx) com resultados estatísticos.  
        graficos/: Figuras de alta resolução (.png) para inclusão no artigo.  
        mapas/: Mapas coropléticos das regiões do Brasil.  
        relatorio_: Relatório com todos os resultados.
        lista_figuras_submissao.csv
        resumo_final_submissao.csv

Acesso aos Dados

Os dados utilizados foram obtidos do DATASUS (Sistema de Informações Hospitalares do SUS), disponíveis publicamente em:
	https://datasus.saude.gov.br/
		ulilizamos a biblioteca pysus para facilitar o download dos microdados

Instruções para Reprodução:  

    Baixe os arquivos Parquet do SIH/SUS referentes aos anos de 2016 a 2025.  
    Organize-os na pasta data/ seguindo o padrão de nomeação: SIH_{ANO}.Parquet.  
    Certifique-se de que os dados contenham as colunas:
    	["ESTADO_ORIGEM", "PROC_REA", "VAL_TOT", "DIAS_PERM", "IDADE", "SEXO"]  

    

Requisitos de Software

Para reproduzir a análise, utilize o ambiente Python especificado no arquivo requirements.txt (anexo a este documento).  
Passos para Execução:

    Crie um ambiente virtual:
    	python -m venv ambiente_artigo  
	source ambiente_artigo/bin/activate  # Linux/Mac  
	.\ambiente_artigo\Scripts\activate   # Windows  

Instale as dependências:  

	pip install -r requirements.txt  

Execute o script:  

jupyter nbconvert --to notebook --execute analise.ipynb 

    ou abra dentro da sua IDE
	Observação: O tempo de execução varia conforme o hardware.  

Saídas Geradas

Todos os resultados são salvos automaticamente na pasta resultados_analise_bariatrica/:  

    Tabelas: Formato .xlsx compatível com editores de texto (ex.: Word).  
    Gráficos e mapas: Resolução de 600 DPI para publicação científica.  
