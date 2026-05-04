🛡️ Segurança Pública · Municípios do Pará
Dashboard interativo de análise de segurança pública dos municípios do estado do Pará, com visualização geoespacial, rankings, histórico mensal e análise de vizinhança.

📸 Visão Geral
Aplicação web 100% client-side (sem backend) que carrega um GeoJSON municipal e agrega dados de ocorrências criminais diretamente no navegador, exibindo:

🗺️ Mapa coroplético interativo por município
📊 Gráficos de ranking, série histórica e comparação mensal
🔗 Análise de vizinhança (epicentros vs. ilhas de segurança)
🧭 Painel por regional de segurança
🔍 Filtros dinâmicos em cascata
🚀 Como Usar
Pré-requisitos
Nenhuma instalação necessária. Basta um navegador moderno.

Executando localmente
Clone o repositório:
bash
Copy
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
Certifique-se de que o arquivo de dados está presente:
📁 projeto/
├── index.html
└── dados_seguranca_puplica_pa.geojson   ← obrigatório
Sirva localmente (necessário por conta do fetch do GeoJSON):
bash
Copy
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .
Acesse no navegador:
http://localhost:8080
⚠️ Não abra o index.html diretamente pelo sistema de arquivos (file://). O carregamento do GeoJSON via fetch requer um servidor HTTP.

📂 Estrutura do Projeto
📁 projeto/
├── index.html                          # Aplicação completa (HTML + CSS + JS)
└── dados_seguranca_puplica_pa.geojson  # Base de dados geoespacial municipal
🗂️ Funcionalidades
🗺️ Aba — Visão
Mapa coroplético com gradiente de cor por indicador selecionado
Tooltip detalhado ao passar o mouse sobre cada município
Clique no município para ver KPIs e detalhes no painel lateral
Narrativa automática contextualizada
🏆 Aba — Ranking
Top 20 municípios em gráfico de barras horizontal
Top 50 municípios em lista com barra de progresso relativa
Ordenação por qualquer indicador
📈 Aba — Histórico
Série mensal de ocorrências (CVLI, Furto, Roubo)
Série mensal de densidades por 100 mil habitantes
Badge indicando filtros ativos
🧭 Aba — Regionais
Comparativo entre regionais de segurança
Gráfico de barras + linha de média
Tabela detalhada por regional
🔗 Aba — Vizinhança
Cálculo de pressão de vizinhança: valor_município − média_vizinhos
🔴 Epicentro: município acima da média dos vizinhos
🔵 Ilha de segurança: município abaixo da média dos vizinhos
Mapa recolorido com gradiente azul → branco → vermelho
Tabela completa ordenada por pressão
📊 Indicadores Disponíveis
Indicador	Tipo	Descrição
CVLI	Contagem	Crimes Violentos Letais Intencionais
Furto	Contagem	Total de furtos registrados
Roubo	Contagem	Total de roubos registrados
Densidade CVLI	Taxa	CVLI por 100 mil habitantes
Densidade Furto	Taxa	Furtos por 100 mil habitantes
Densidade Roubo	Taxa	Roubos por 100 mil habitantes
🔍 Filtros Dinâmicos
Os filtros funcionam em cascata — ao selecionar um, os demais se atualizam automaticamente com as opções disponíveis:

Filtro	Descrição
🧭 Regional	Filtra por regional de segurança pública
🏙️ Cidade	Filtra por município específico
👥 Faixa Populacional	Filtra por porte do município
📅 Mês	Filtra por mês de ocorrência
🛠️ Tecnologias Utilizadas
Tecnologia	Versão	Uso
Leaflet.js	1.9.4	Mapa interativo
Chart.js	4.4.0	Gráficos e visualizações
CartoDB Dark	—	Tiles do mapa base
Google Fonts	—	Source Sans 3 + Source Code Pro
HTML5 / CSS3 / JS Vanilla	—	Toda a lógica da aplicação
📋 Formato do GeoJSON
O arquivo dados_seguranca_puplica_pa.geojson deve conter features com as seguintes propriedades:

json
Copy
{
  "type": "Feature",
  "geometry": { "type": "MultiPolygon", "coordinates": [...] },
  "properties": {
    "CD_MUN": "150010",
    "CIDADE": "Abaetetuba",
    "SIGLA_UF": "PA",
    "regionais": "Regional Tocantins",
    "Faixa": "100k - 500k",
    "Polulação": 160000,
    "AREA_KM2": 1610.5,
    "mes_fato": "JANEIRO",
    "CVLI": 5,
    "FURTO": 120,
    "ROUBO": 80,
    "Densidade CVLI (100milhab)": 3.1,
    "Densidade Furto (100milhab)": 75.0,
    "Densidade Roubo (100milhab)": 50.0
  }
}
Cada feature representa um município em um mês. A aplicação agrega automaticamente todos os meses por município.

⚙️ Arquitetura
loadAll()
  └── fetch(GeoJSON)
        └── processGeoJSON()        → agrega por município e regional
              ├── initMap()         → Leaflet + CartoDB tiles
              ├── populateFilters() → dropdowns em cascata
              ├── buildMapLayer()   → camada coroplética
              ├── buildRanking()    → top 50 municípios
              ├── buildHistory()    → séries mensais
              ├── buildRegionais()  → painel por regional
              └── buildVizinhanca() → análise de pressão espacial
📄 Licença
Este projeto está sob a licença MIT.

🤝 Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.
