# Projeto Final DS-PY-004 - Análise de Acidentes em Rodovias Federais

**Equipe:** Allen Carneiro, Américo, Andre
**Base:** DATATRAN 2025 - Acidentes registrados pela PRF
**Fonte:** Portal de Dados Abertos PRF / https://www.gov.br/prf/pt-br/acesso-a-informacao/dados-abertos

## 📊 Sobre a base
- **72.529 linhas** x 30 colunas
- **Recorte temporal:** 01/01/2025 a 31/12/2025
- **3 colunas numéricas:** km, feridos, mortos, veículos, latitude, longitude
- **Categóricas:** uf, tipo_acidente, causa_acidente, classificacao_acidente, dia_semana, fase_dia

Dicionário: `id` (registro), `uf` (estado), `br` (rodovia), `causa_acidente`, `tipo_acidente`, `classificacao_acidente` (Sem Vítimas, Com Vítimas Feridas, Com Vítimas Fatais)

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
