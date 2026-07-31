📊 Panorama do Mercado de Dados no Brasil (2024–2025)

Análise do mercado de trabalho para profissionais de dados no Brasil, utilizando Python, SQL e Power BI, a partir do dataset público State of Data Brazil 2024–2025 (Data Hackers / Kaggle).

O objetivo do projeto foi percorrer todo o fluxo de um projeto real de análise de dados: da limpeza e tratamento em Python, passando por consultas SQL, até a construção de um dashboard interativo no Power BI — contando uma história com os dados sobre salários, cargos, nível de experiência, gênero, idade e região no mercado de dados brasileiro.

🎯 Sobre o projeto

Profissionais de dados frequentemente lidam com dúvidas como: "Quanto ganha um Analista de Dados Sênior?", "O mercado é mais concentrado em qual região do país?", "Quanto tempo leva para evoluir de Júnior a Sênior?".

Este projeto responde a essas perguntas de forma visual e orientada a dados, simulando o processo de um analista que recebe uma base bruta de pesquisa, precisa tratá-la, extrair insights e comunicá-los de forma clara para stakeholders — com Python para o tratamento e exploração inicial, SQL para consultas analíticas e Power BI para o dashboard final.

🗂️ Fonte dos dados
Dataset: State of Data Brazil 2024–2025 — pesquisa anual da comunidade Data Hackers sobre o mercado de dados no Brasil
Volume: 3.818 respondentes analisados após tratamento
Licença: dados públicos disponibilizados para fins educacionais/análise
🛠️ Tecnologias utilizadas
Etapa	Ferramentas
Tratamento e exploração	Python (Pandas, NumPy, Matplotlib, Seaborn)
Armazenamento e consultas	SQLite + SQL
Visualização e dashboard	Power BI
Ambiente de desenvolvimento	Jupyter Notebook
📁 Estrutura do projeto
├── analise_mercado_dados.ipynb      # Notebook com todo o tratamento e EDA em Python
├── data/
│   ├── Final Dataset - State of Data 2024 - Kaggle - df_survey_2024.csv   # Dados brutos
│   ├── dados_tratados.csv           # Dados limpos e prontos para análise
│   └── mercado_dados.db             # Banco SQLite com a tabela "profissionais"
├── imagens/                         # Gráficos exportados do notebook
├── dashboard/                       # Arquivo .pbix do Power BI
└── README.md
🔄 Etapas do projeto
1. Tratamento de dados (Python)
Seleção das colunas relevantes da pesquisa bruta (idade, gênero, raça/etnia, região, escolaridade, cargo, nível, faixa salarial, tempo de experiência, satisfação)
Renomeação de colunas para nomes legíveis
Remoção de registros sem cargo informado
Conversão de faixas salariais em valores numéricos representativos (salario_num) para permitir cálculos de média
Padronização de categorias de cargo e escolaridade (ex: agrupar variações de nomenclatura em categorias únicas)
Conversão do tempo de experiência em valores numéricos médios por faixa
2. Análise exploratória (Python)

Geração de estatísticas descritivas e visualizações com Seaborn/Matplotlib para entender a distribuição de salário, cargos, nível, gênero, faixa etária, escolaridade, raça/etnia, região e satisfação profissional.

3. Consultas SQL

Os dados tratados foram persistidos em um banco SQLite (mercado_dados.db), permitindo consultas analíticas como:

Salário médio por nível
Top 5 cargos por salário médio
Percentual de satisfação por região
Cruzamento cargo × nível × salário médio
4. Dashboard (Power BI)

Construção de um painel interativo consolidando os principais indicadores em uma única visão executiva.

💡 Principais insights

Salário cresce de forma expressiva com o nível de senioridade A média salarial salta de R$ 4.160 (Júnior) para R$ 8.050 (Pleno) e R$ 14.600 (Sênior) — um crescimento de mais de 250% do início ao topo da carreira.

<img width="1184" height="732" alt="salario_por_nivel" src="https://github.com/user-attachments/assets/0f81d530-d685-43ae-bb6c-e8d075429079" />


Cargos técnicos especializados lideram em remuneração Arquiteto de Dados e Engenheiro de Machine Learning aparecem no topo do ranking salarial (~R$ 15,9 mil), à frente inclusive de Engenheiro de Dados e Product Manager.

<img width="1184" height="732" alt="salario_por_cargo" src="https://github.com/user-attachments/assets/714116c8-d609-4159-b2fc-ab34cc93aee2" />


Mercado concentrado, mas com boa distribuição salarial A região Sudeste concentra quase 60% dos profissionais (2.237 de 3.818), mas curiosamente não é onde a satisfação profissional é maior — as diferenças salariais médias entre regiões são menores do que a diferença de volume de profissionais.

<img width="1184" height="731" alt="qtd_regiao" src="https://github.com/user-attachments/assets/a26ca93a-69a6-4130-94b8-7a9b6d6df3f5" />


Mercado ainda predominantemente masculino 75,2% dos respondentes se identificam como homens, contra 24,8% mulheres — reforçando a discussão sobre equidade de gênero na área de dados/tecnologia.

<img width="642" height="640" alt="contagem_genero" src="https://github.com/user-attachments/assets/04e73e16-1903-4abf-a12b-38d32414a799" />


Perfil etário jovem A maior concentração de profissionais está entre 25 e 34 anos (mais de 2.300 pessoas), indicando um mercado em expansão e ainda recente no Brasil.

<img width="1184" height="731" alt="qtd_faixa_idade" src="https://github.com/user-attachments/assets/b8a4b890-7855-4962-9da2-a2ae38ebe7c9" />


Tempo de experiência acompanha o nível Em média, profissionais Sênior têm 6 anos de experiência na área de dados, contra 3,2 anos (Pleno) e 1,4 anos (Júnior) — validando a consistência da segmentação de nível usada na pesquisa.

<img width="1184" height="732" alt="tempo_por_nivel_exp" src="https://github.com/user-attachments/assets/df1bbec8-a5c7-4629-a4e4-db7621ccd9c7" />


📈 Dashboard Power BI

O dashboard final consolida os principais KPIs em um painel único, com visão geral do mercado (total de profissionais, média salarial, % de satisfação) e recortes por nível, gênero, faixa etária, região e cargo.

<img width="1116" height="649" alt="image" src="https://github.com/user-attachments/assets/fa6163a0-80d4-4edb-946a-1700726f11be" />


Principais elementos do dashboard:

KPIs: total de profissionais, média salarial geral e % de satisfação
Salário médio por nível (Júnior/Pleno/Sênior)
Distribuição por gênero
Distribuição por faixa etária
Distribuição por região
Salário médio por cargo (Top 8)
▶️ Como reproduzir o projeto
bash
# Clone o repositório
git clone https://github.com/didifernandes/SEU-REPOSITORIO.git

# Instale as dependências
pip install pandas numpy matplotlib seaborn

# Execute o notebook
jupyter notebook analise_mercado_dados.ipynb

O notebook gera automaticamente data/dados_tratados.csv e data/mercado_dados.db, que podem ser conectados diretamente ao Power BI para reconstruir o dashboard.
