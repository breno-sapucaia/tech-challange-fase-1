# Hepatitis C Prediction Model

Este projeto contém um modelo de machine learning para predição de Hepatite C baseado em exames laboratoriais, desenvolvido para determinar se um paciente pode ser um doador de sangue.

## 📋 Sobre o Projeto

O modelo utiliza algoritmos de classificação (Decision Tree e KNN) para analisar marcadores bioquímicos e determinar se um paciente está apto para doação de sangue. Os principais indicadores analisados incluem:

- **AST** (Aspartato Aminotransferase)
- **GGT** (Gama-Glutamil Transferase) 
- **BIL** (Bilirrubina)
- **ALB** (Albumina)
- **CHE** (Colina Esterase)
- E outros marcadores laboratoriais

## 🐳 Executando com Docker

### Pré-requisitos
- Docker instalado no seu sistema
- Git (opcional, para clonar o repositório)

### Passo a Passo

#### 1. **Construir a imagem Docker**
```bash
docker build -t hepatitis-prediction .
```

#### 2. **Executar o container**
```bash
docker run -p 8888:8888 -v $(pwd):/app hepatitis-prediction
```

#### 3. **Acessar o Jupyter Notebook**
- Abra seu navegador e acesse: `http://localhost:8888`
- O notebook `hc-model-prediciton.ipynb` estará disponível

### 🚀 Comandos Alternativos

#### **Executar em background**
```bash
docker run -d -p 8888:8888 --name hepatitis-model hepatitis-prediction
```

#### **Executar com volume persistente**
```bash
docker run -p 8888:8888 -v $(pwd)/data:/app/data hepatitis-prediction
```

### 📊 Resultados do Modelo

O modelo apresenta as seguintes métricas:

**Decision Tree Classifier:**
- Acurácia: 94.3%
- Precision: 97% (classe saudável), 76% (classe doente)
- Recall: 96% (classe saudável), 81% (classe doente)

**KNN Classifier:**
- Acurácia: 95.9%
- Precision: 96% (classe saudável), 92% (classe doente)
- Recall: 99% (classe saudável), 75% (classe doente)

## 🛠️ Desenvolvimento Local

### Instalação Manual
```bash
# Criar ambiente virtual
python -m venv venv
source .venv/bin/activate  # macOS/Linux
# ou
venv\Scripts\activate     # Windows

# Instalar dependências
pip install -r requirements.txt

# Executar Jupyter
jupyter notebook
```

## 📁 Estrutura do Projeto

```
tech_challange_fase_1/
├── Dockerfile                    # Configuração do Docker
├── requirements.txt             # Dependências Python
├── hc-model-prediciton.ipynb    # Notebook principal
├── HepatitisCdata.csv           # Dataset
├── README.md                    # Este arquivo
└── Tech Challenge IADT - Fase 1.pdf  # Documentação
```

---
# Continuidade da fase 2
Análise dos modelos para otimização

Performance atual (com SMOTE):
- XGBoost: AUC = 1.00, Acurácia = 98.4% — quase perfeito
- Decision Tree: Acurácia = 96.7% — espaço para melhoria
- KNN: Acurácia = 95.9% — espaço para melhoria
Recomendação: Decision Tree

objetivo é melhorar o decision tree que possui um espaço de melhoria, pequeno, mas possui.
