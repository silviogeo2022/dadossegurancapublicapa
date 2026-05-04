# 🛡️ Segurança Pública · Municípios do Pará

> Dashboard interativo de análise de segurança pública dos municípios do estado do Pará, com visualização geoespacial, rankings, histórico mensal e análise de vizinhança.

---

## 📸 Visão Geral

Aplicação web **100% client-side** (sem backend) que carrega um GeoJSON municipal e agrega dados de ocorrências criminais diretamente no navegador.

### Principais Recursos:

*   🗺️ **Mapa Coroplético:** Visualização interativa por município com gradiente de cor por indicador.
*   📊 **Gráficos Dinâmicos:** Rankings, série histórica e comparativos mensais usando Chart.js.
*   🔗 **Análise de Vizinhança:** Identificação de epicentros e ilhas de segurança.
*   🧭 **Painel Regional:** Dados agregados por regionais de segurança pública.
*   🔍 **Filtros em Cascata:** Refinamento por regional, cidade, faixa populacional e mês.
*   📋 **Narrativa Automática:** Contextualização textual gerada automaticamente ao selecionar um município.

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

3.  **Inicie um servidor local:** (Obrigatório para carregar o GeoJSON via `fetch`)
    *   **Python:** `python -m http.server 8080`
    *   **Node.js:** `npx serve .`

4.  **Acesse no navegador:** `http://localhost:8080`

> ⚠️ **Não abra o `index.html` diretamente pelo sistema de arquivos (`file://`).** O carregamento do GeoJSON via `fetch` requer um servidor HTTP.

---

## 📁 Estrutura do Projeto
