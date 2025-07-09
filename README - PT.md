# ChemML - Sistema de Predição de Propriedades Moleculares

## Visão Geral

ChemML é um sistema completo de predição de propriedades moleculares que combina técnicas de Machine Learning com química computacional. Permite que usuários insiram moléculas (via SMILES) e obtenham predições confiáveis de propriedades físico-químicas essenciais.

## Objetivos do Projeto

* **Técnico:** Demonstrar aplicação de ML em problemas científicos reais.
* **Profissional:** Exibir habilidades em Flask, PyTorch, APIs REST e bancos de dados.
* **Diferencial:** Aplicar conhecimento químico para feature engineering e validação das predições.

## Funcionalidades Principais

1. **Predição de Propriedades**

   * Solubilidade em água (regressão LogS)
   * Toxicidade aguda (classificação binária)
   * Ponto de fusão (regressão de temperatura)
   * Biodegradabilidade ambiental (classificação)

2. **Interface Web**

   * Upload de moléculas via SMILES ou desenho molecular
   * Visualização 2D/3D das estruturas
   * Histórico de predições por usuário
   * Dashboard com estatísticas de uso e performance

3. **API REST**

   * Endpoints para integração externa
   * Autenticação JWT
   * Documentação automática (Swagger)
   * Rate limiting e caching

4. **Sistema de Validação**

   * Validação química de SMILES
   * Detecção de moléculas fora do domínio de aplicação
   * Avaliação de confiabilidade das predições

## Arquitetura do Sistema

```
chemml/chemml/
├── app/
│   ├── models/           # Modelos PyTorch e banco de dados (SQLAlchemy)
│   ├── routes/           # Endpoints API, autenticação e interface web
│   ├── utils/            # Cálculo de descritores, validadores e pré-processamento
│   └── templates/        # Páginas HTML: base, index, predict, history
├── data/
│   ├── raw/              # Dados brutos
│   ├── processed/        # Dados pré-processados
│   └── models/           # Modelos treinados
├── notebooks/            # Exploração, desenvolvimento e avaliação de modelos
├── tests/                # Testes unitários e de integração
├── config.py             # Configurações de ambiente
├── requirements.txt      # Dependências do projeto
└── README.md             # Documentação principal
```

## Stack Tecnológica

* **Backend:** Flask, SQLAlchemy, PyTorch, RDKit, Pandas/NumPy
* **Frontend:** HTML/CSS/JavaScript, Bootstrap, Chart.js
* **Banco de Dados:** SQLite (desenvolvimento), PostgreSQL (produção)
* **Deployment:** Docker, Gunicorn, Nginx, Redis

## Datasets Sugeridos

* **Solubilidade:** AqSolDB, ESOL
* **Toxicidade:** Tox21, ChEMBL
* **Ponto de Fusão:** Bradley Melting Point, NIST WebBook

## Métricas de Avaliação

* **Regressão:** R², RMSE, MAE
* **Classificação:** Acurácia, F1-Score, AUC-ROC

## Cronograma de Desenvolvimento

1. **Fase 1 (Semanas 1-2):**

   * Configuração do ambiente e estrutura do projeto
   * Coleta e preparação de datasets
   * Implementação de pré-processamento molecular
   * Criação do esquema do banco de dados

2. **Fase 2 (Semanas 3-4):**

   * Desenvolvimento e treinamento de modelos ML
   * Otimização de hiperparâmetros e pipeline de validação

3. **Fase 3 (Semanas 5-6):**

   * Implementação da API REST e autenticação
   * Integração dos modelos com a API
   * Testes

4. **Fase 4 (Semanas 7-8):**

   * Desenvolvimento da interface web e dashboard
   * Visualizações moleculares e histórico de usuários

5. **Fase 5 (Semanas 9-10):**

   * Documentação completa e testes finais
   * Deploy e otimizações de performance

## Deployment

1. Build da imagem Docker:

   ```bash
   docker build -t chemml .
   ```
2. Execução com Gunicorn e Nginx:

   ```bash
   docker run -d -p 80:80 chemml
   ```
3. Serviços adicionais: Redis para cache e sessões.

## Uso

1. Clone o repositório:

   ```bash
   git clone https://github.com/brunohenses/chemml.git
   cd chemml
   ```
2. Configure o ambiente virtual e instale dependências:

   ```bash
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Inicialize o banco de dados:

   ```bash
   flask db init && flask db migrate && flask db upgrade
   ```
4. Execute o servidor:

   ```bash
   flask run
   ```

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e pull requests.

## Licença

Este projeto está licenciado sob a MIT License.
