# Projeto Final DS-PY-004 - Análise de Acidentes em Rodovias Federais

**Equipe:** Allen Carneiro, Américo, Andre
**Base:** DATATRAN 2025 - Acidentes registrados pela PRF
**Fonte:** Portal de Dados Abertos PRF / https://www.gov.br/prf/pt-br/acesso-a-informacao/dados-abertos

## 📊 Sobre a base
- **72.529 linhas** x 30 colunas
- **Recorte temporal:** 01/01/2025 a 31/12/2025
- **6 colunas numéricas:** km, feridos, mortos, veículos, latitude, longitude
- **Categóricas:** uf, tipo_acidente, causa_acidente, classificacao_acidente, dia_semana, fase_dia

📖 Dicionário Simplificado

| Campo                   | Descrição                                  |
| ----------------------- | ------------------------------------------ |
| id                      | Identificador da ocorrência                |
| uf                      | Unidade Federativa                         |
| br                      | Rodovia Federal                            |
| km                      | Quilômetro da ocorrência                   |
| municipio               | Município da ocorrência                    |
| tipo\_acidente          | Tipo do acidente registrado                |
| causa\_acidente         | Causa informada pela PRF                   |
| classificacao\_acidente | Sem vítimas, com vítimas feridas ou fatais |
| mortos                  | Número de vítimas fatais                   |
| feridos                 | Quantidade total de feridos                |


🧹 Limpeza e Transformação dos Dados

As principais etapas de preparação da base foram:

- Identificação e tratamento de valores faltantes;
- Verificação de registros duplicados;
- Conversão de tipos de dados (datas e variáveis numéricas);
- Padronização de categorias textuais;
- Análise de outliers utilizando IQR por UF;
- Criação de variáveis derivadas para enriquecer as análises.

Decisões adotadas

- Valores ausentes em classificacao_acidente, regional, delegacia e uop foram preenchidos com "não informado" por representarem ausência de preenchimento operacional.
- A coluna km apresentou aproximadamente 36,7% de valores ausentes e foi mantida como NaN, pois não era necessária para as análises principais e sua imputação poderia introduzir viés.
- Não foram identificados registros duplicados.
- As colunas categóricas foram padronizadas para evitar inconsistências de grafia e capitalização.

## ❓ Perguntas definidas ANTES da análise
1. Quais tipos de acidente são mais frequentes e o que isso indica sobre comportamento?
2. Quais estados concentram mais acidentes e por quê?
3. O período do dia e o dia da semana influenciam na frequência e gravidade?
4. Quais causas estão mais associadas a acidentes fatais?
5. Existe relação entre tipo de pista/traçado e gravidade?

## 🚀 Como reproduzir
```bash
git clone https://github.com/seu-usuario/seu-projeto.git
cd seu-projeto
pip install pandas numpy matplotlib seaborn
jupyter notebook notebooks/analise.ipynb
```

## 📁 Estrutura
```
seu-projeto/
├── README.md
├── .gitignore
├── dados/
│   └── datatran2025.csv (72.529 registros, fonte PRF)
└── notebooks/
    └── analise.ipynb (com saídas executadas)
```

## 🔍 Principais achados
1. Colisão Traseira lidera com 19,8% - indica falta de distância segura
2. MG, SC e PR somam 35% dos casos por maior malha federal
3. Manhã e tarde concentram 62% dos acidentes (fluxo casa-trabalho)
4. Colisão frontal representa 44% das mortes (dados PRF)

## ⚠️ Limitações
- Base só cobre BRs, não vias municipais/estaduais
- km com 36,7% faltante - não permite análise espacial precisa por km
- Sem dados de volume de tráfego para taxa por veículo

## 🔜 Próximos passos
- Cruzar com dados de frota DENATRAN e volume DNIT para taxa por 1000 veículos
- Modelo preditivo de gravidade com Random Forest
- Dashboard interativo com mapa de calor

## 📝 Git
- Branch main + feat/limpeza
- 15+ commits com mensagens descritivas

## 📝 Controle de Versão
Repositório GitHub público.
Histórico de commits distribuído entre os integrantes.
Mensagens de commit descritivas seguindo boas práticas.
Controle de evolução do projeto através do Git.
