# 🛡️ Segurança Pública · Municípios do Pará

> Dashboard interativo de análise de segurança pública dos municípios do estado do Pará, com visualização geoespacial, rankings, histórico mensal e análise de vizinhança.

---

## 📸 Visão Geral

Aplicação web **100% client-side** (sem backend) que carrega um GeoJSON municipal e agrega dados de ocorrências criminais diretamente no navegador.

### Principais Recursos:
*   🗺️ **Mapa Coroplético:** Visualização interativa por município.
*   📊 **Gráficos Dinâmicos:** Rankings, série histórica e comparativos mensais usando Chart.js.
*   🔗 **Análise de Vizinhança:** Identificação de epicentros e ilhas de segurança.
*   🧭 **Painel Regional:** Dados agregados por regionais de segurança.
*   🔍 **Filtros em Cascata:** Refinamento por regional, cidade, faixa populacional e mês.

---

## 🚀 Como Usar

### Pré-requisitos
Nenhuma instalação é necessária, apenas um navegador moderno.

### Executando Localmente
1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    cd seu-repositorio
    ```
2.  **Verifique os arquivos:** Certifique-se de que o arquivo `dados_seguranca_puplica_pa.geojson` está na mesma pasta do `index.html`.
3.  **Inicie um servidor local:** (Obrigatório para carregar o GeoJSON via fetch)
    *   **Python:** `python -m http.server 8080`
    *   **Node.js:** `npx serve .`
4.  **Acesse:** `http://localhost:8080`

---

## 📊 Indicadores Disponíveis

| Indicador | Tipo | Descrição |
| :--- | :--- | :--- |
| **CVLI** | Contagem | Crimes Violentos Letais Intencionais |
| **Furto** | Contagem | Total de furtos registrados |
| **Roubo** | Contagem | Total de roubos registrados |
| **Densidade** | Taxa | Ocorrências por 100 mil habitantes |

---

## 🔗 Análise de Vizinhança (Pressão Espacial)

A ferramenta calcula automaticamente a pressão de segurança baseada na geografia:
*   🔴 **Epicentro:** Município com índices significativamente maiores que seus vizinhos diretos.
*   🔵 **Ilha de Segurança:** Município com índices menores que a média da sua vizinhança.

---

## 🛠️ Tecnologias Utilizadas

*   [Leaflet.js](https://leafletjs.com/) - Mapas interativos.
*   [Chart.js](https://www.chartjs.org/) - Gráficos performáticos.
*   [CartoDB](https://carto.com/basemaps/) - Camada de mapa (Dark Matter).
*   [Google Fonts](https://fonts.google.com/) - Tipografia (Source Sans 3).

---

## 🤝 Contribuições

Issues e Pull Requests são bem-vindos!

---

<div align="center">
  Desenvolvido para análise de dados governamentais do estado do Pará.
</div>
