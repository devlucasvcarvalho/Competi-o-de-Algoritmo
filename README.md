# 🧠 Competição de Algoritmo 1 — Inteligência Computacional Aplicada

**Professor:** Roney Nogueira de Sousa  
**Disciplina:** Inteligência Computacional Aplicada  

## 📘 Descrição

Este projeto implementa a solução da **Competição de Algoritmo 1**, conforme o edital fornecido pelo professor.  
O objetivo é avaliar o desempenho de algoritmos de **classificação supervisionada** em três bases de dados sintéticas clássicas:  
- `Two Moons`  
- `Banana`  
- `Ripley`  

O modelo escolhido foi um **Perceptron Multicamadas (MLP)** com **duas camadas ocultas de 5 neurônios cada**, desenvolvido em Python utilizando a biblioteca `scikit-learn`.

---

## ⚙️ Estrutura do Projeto

├── notebook/
│ └── Competicao_Algoritmo1.ipynb # Notebook Colab completo e reprodutível
├── models/
│ └── mlp_two_moons.joblib # Modelo salvo (exemplo)
├── predict.py # Script de inferência padronizado
├── README.md # Este arquivo
└── requirements.txt # Dependências do projeto


---

## 🚀 Como Executar o Projeto

### 🔹 1. Executar o Notebook no Google Colab

1. Acesse o Google Colab: [https://colab.research.google.com](https://colab.research.google.com)
2. Faça upload do arquivo `Competicao_Algoritmo1.ipynb`.
3. Execute **todas as células em ordem** (Menu → Executar tudo).  
4. O notebook:
   - Gera e/ou baixa os datasets (`Two Moons`, `Banana`, `Ripley`);
   - Treina o modelo MLP;
   - Avalia as métricas de desempenho (Acurácia, Precisão, Recall, F1);
   - Calcula o tempo médio de inferência por amostra (30 execuções).

---

### 🔹 2. Inferência via Script (`predict.py`)

Após treinar o modelo, é possível realizar previsões com o script de inferência padronizado:

```bash
python predict.py <modelo.joblib> <arquivo_de_entrada.csv> [arquivo_de_saida.csv] 

Exemplo:

python predict.py models/mlp_two_moons.joblib datasets/two_moons.csv preds.csv


O script gera um arquivo preds.csv com as previsões (y_pred).

🧩 Modelo Utilizado

Tipo: MLPClassifier (Multi-Layer Perceptron)
Biblioteca: scikit-learn
Parâmetros:

MLPClassifier(
    hidden_layer_sizes=(5,5),
    activation='relu',
    solver='adam',
    max_iter=1000,
    random_state=42
)


O modelo foi avaliado com validação cruzada StratifiedKFold (k=5) e 30 medições de tempo por amostra, conforme o edital da competição.

📈 Métricas Avaliadas

Para cada dataset:

Acurácia

Precisão (macro)

Recall (macro)

F1-score (macro)

Tempo médio de inferência por amostra

Desvios-padrão das métricas nas dobras da validação cruzada

O score final S segue o critério:

S = 0.70·M - 0.20·σM + 0.10·T*


onde:

M é a média das métricas (Acc, Prec, Rec, F1);

σM é a média dos desvios-padrão;

T* é a normalização min–max inversa do tempo médio de inferência.

🧾 Dependências

As principais bibliotecas utilizadas foram:

scikit-learn==1.5.0
pandas==2.2.2
numpy==1.26.4
matplotlib==3.9.0
wget==3.2
joblib==1.4.2


No Colab, as dependências são instaladas automaticamente com:

!pip install -q scikit-learn pandas matplotlib numpy wget joblib

🔒 Reprodutibilidade

Todas as sementes aleatórias (numpy, random) foram fixadas com SEED = 42.

O notebook é totalmente reprodutível e roda do zero.

Não foram utilizados frameworks AutoML.

Foram respeitados os protocolos de validação e as regras do edital.

✍️ Observações

O modelo é leve, estável e possui baixo tempo de inferência.

O relatório técnico com métricas e análises está incluído em PDF na submissão.

Este repositório segue as regras de submissão descritas no edital da competição.
