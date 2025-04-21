# WindXsar - Análise de Vento Oceânico com Imagens SAR

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) <!-- Exemplo: Adicione um badge de licença -->

Este repositório contém um notebook Jupyter (`analise_vento_furacao.ipynb`) para analisar imagens de Radar de Abertura Sintética (SAR) e estimar a direção e intensidade do vento na superfície do mar, utilizando bibliotecas como `xsar` e `xsarsea`.

## Objetivo do Projeto

O objetivo é demonstrar um fluxo de trabalho para processar dados SAR (possivelmente de missões como Sentinel-1, RADARSAT-2, RCM - *confirmar fontes de dados usadas*) para extrair informações sobre o campo de vento sobre o oceano, focando em eventos como furacões (*confirmar o foco do notebook*).

## Tecnologias e Bibliotecas Principais

*   Python 3.11 (ou superior)
*   Jupyter Notebook / JupyterLab
*   **Bibliotecas Principais:**
    *   `xsar` / `xsarsea`: Processamento de dados SAR
    *   `xarray`, `dask`: Manipulação de dados multidimensionais e computação paralela
    *   `numpy`, `scipy`, `pandas`: Computação científica e análise de dados
    *   `matplotlib`, `holoviews`, `geoviews`: Visualização de dados
    *   `gdal`: Manipulação de dados geoespaciais
    *   `python-snappy`: (Opcional, dependendo do fluxo de trabalho do SNAP)

## Instalação

Recomenda-se o uso de um ambiente virtual (como Conda ou venv) para gerenciar as dependências.

**Opção 1: Usando Conda (Recomendado devido ao GDAL)**

1.  Clone o repositório:
    ```
    git clone https://github.com/BayesTheory/WindXsar.git
    cd WindXsar
    ```
2.  Crie um ambiente Conda (você pode criar um arquivo `environment.yml` para facilitar):
    ```
    # Exemplo de como criar diretamente (ou use um environment.yml)
    conda create -n windsar python=3.11
    conda activate windsar
    conda install numpy scipy pandas matplotlib gdal dask holoviews geoviews -c conda-forge
    # Instalar xsar e dependências específicas via pip dentro do ambiente conda
    pip install python-snappy xsar xsar[S1,RS2,RCM] xsarsea
    ```
    *(Nota: A instalação do GDAL via Conda é geralmente mais fácil do que via pip).*

**Opção 2: Usando Pip e `requirements.txt`**

1.  Clone o repositório:
    ```
    git clone https://github.com/BayesTheory/WindXsar.git
    cd WindXsar
    ```
2.  Crie e ative um ambiente virtual:
    ```
    python -m venv venv
    source venv/bin/activate # Linux/Mac
    # venv\Scripts\activate # Windows
    ```
3.  Instale as dependências (certifique-se que `requirements.txt` está correto e inclui *todas* as libs listadas):
    ```
    pip install -r requirements.txt
    ```
    *(Nota: A instalação do GDAL via pip pode exigir dependências de sistema pré-instaladas).*

## Uso

1.  Ative o ambiente virtual (`conda activate windsar` ou `source venv/bin/activate`).
2.  Inicie o Jupyter Notebook ou JupyterLab:
    ```
    jupyter notebook
    # ou
    jupyter lab
    ```
3.  Abra o notebook `analise_vento_furacao.ipynb` (ou o nome correto) e execute as células.

*(Opcional: Adicionar informações sobre onde obter dados de exemplo ou quais dados são necessários para rodar o notebook).*

## Exemplo de Saída

![WindField Points with Angle Direction (deg)](https://github.com/BayesTheory/xsar/assets/47011842/026fc43f-1ea9-4f85-b3bc-49345d25803d)

## Licença

Distribuído sob a licença XYZ. Veja `LICENSE` para mais informações. *(Adicione um arquivo LICENSE se ainda não houver)*.

