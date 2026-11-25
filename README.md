# 📊 NUCLENAI — Dataset & Pipeline de Dados

Repositório contendo os dados brutos, dados tratados e notebooks Jupyter responsáveis pela análise exploratória (EDA), limpeza e ingestão dos registros de telemetria operacional de uma usina nuclear industrial para banco de dados MySQL em nuvem.

## 📁 Estrutura do Repositório

```text
dataset/
├── 07_monitoramento_usina_nuclear_industrial.csv           # Dataset bruto original
├── 07_monitoramento_usina_nuclear_industrial_TRATADOS.csv  # Dataset limpo e normalizado
├── Dataset-Usina.ipynb                                     # Notebook de análise exploratória e tratamento
└── Database - Nuvem.ipynb                                  # Notebook de conexão e carga no MySQL (RDS/Cloud)
```

## 📋 Variáveis Monitoradas

O conjunto de dados contempla medições físico-químicas e operacionais organizadas por data/hora, circuito (`Primario`, `Geracao`, `Contencao`), turno (`Manha`, `Tarde`, `Noite`) e status operacional:

* **Temperatura (`temperatura_c`)**: Temperatura operacional em graus Celsius (°C).
* **Pressão (`pressao_bar`)**: Pressão do sistema em bar.
* **Vazão (`vazao_m3_h`)**: Vazão do fluido em metros cúbicos por hora ($m^3/h$).
* **Potência (`potencia_mw`)**: Potência gerada em megawatts (MW).
* **Radiação (`radiacao_msv_h`)**: Nível de radiação em milisieverts por hora (mSv/h).
* **Vibração (`vibracao_mm_s`)**: Vibração mecânica em milímetros por segundo (mm/s).
* **Nível de Refrigerante (`nivel_refrigerante_pct`)**: Percentual do nível de líquido refrigerante (%).
* **Eficiência Térmica (`eficiencia_termica_pct`)**: Rendimento térmico do ciclo (%).

## 🚀 Como Executar

1. **Pré-requisitos**: Python 3.9+ e Jupyter Notebook ou Google Colab.
2. **Instale as dependências**:
   ```bash
   pip install pandas sqlalchemy pymysql googledrivedownloader
   ```
3. **Tratamento de Dados**: Execute `Dataset-Usina.ipynb` para reproduzir a inspeção de tipos, tratamento de inconsistências e geração do arquivo `_TRATADOS.csv`.
4. **Carga no Banco**: Execute `Database - Nuvem.ipynb` informando o usuário, senha e endpoint da instância MySQL para criar a base e popular as tabelas.