# 💡 Predição de Gênero com Amazon SageMaker

## 🧠 Descrição do Projeto

Este projeto realiza o **treinamento e avaliação de um modelo de Machine Learning** capaz de prever o **gênero (masculino ou feminino)** com base em **primeiros nomes**.

O modelo utiliza o algoritmo **XGBoost** hospedado e treinado na **plataforma AWS SageMaker**.

O dataset combina nomes e gêneros a partir de **fontes governamentais abertas** dos EUA, Reino Unido, Canadá e Austrália, contendo as contagens e probabilidades associadas a cada nome.

---

## 📊 Objetivo

Criar, treinar e avaliar um modelo de classificação binária (0 = Feminino, 1 = Masculino) utilizando técnicas de:
- Pré-processamento de dados.
- Transformações logarítmicas para redução de outliers.
- Extração de features derivadas do nome.
- Treinamento em nuvem com Amazon SageMaker.
- Avaliação com métricas de desempenho e curva ROC.

---

## ⚙️ Etapas Principais

1. **Importação e análise do dataset**
   - Leitura dos dados via URL.
   - Exploração inicial e estatísticas descritivas.

2. **Transformações no dataset**
   - Aplicação de `np.log1p()` na coluna `Count` para suavizar outliers.
   - Mapeamento do gênero para valores binários (`F → 0`, `M → 1`).
   - Criação de novas features:
     - `Name_len` → comprimento do nome.
     - `vowel_count` → quantidade de vogais.
     - `vowel_end` → se termina com vogal.
   - Remoção da coluna `Name`.

3. **Separação dos dados**
   - Método Hold-Out:
     - 80% treino
     - 10% validação
     - 10% teste

4. **Treinamento com SageMaker**
   - Envio dos datasets para o S3.
   - Configuração do modelo XGBoost.
   - Treinamento e deploy da instância no SageMaker.

5. **Avaliação do modelo**
   - Cálculo das métricas:
     - Sensibilidade (TPR)
     - Especificidade (TNR)
     - Precisão
     - Falsos Positivos / Negativos
     - Acurácia
     - Curva ROC e AUC
   - Exibição da Matriz de Confusão.
   - Geração do gráfico ROC-Curve.

6. **Predição**
   - Seleção de uma linha do dataset de teste.
   - Envio da amostra para o endpoint do SageMaker.
   - Obtenção da probabilidade e classificação final.

---

## 🧩 Dependências

Instale as bibliotecas necessárias:

```bash
pip install -r requirements.txt
```

### ☁️ Execução do Projeto
🔹 Passo 1 – Clonar o repositório

```bash
git clone https://github.com/seu-usuario/nome-do-repo.git
cd nome-do-repo
```

### 🔹 Passo 2 – Instalar as dependências

```bash
pip install -r requirements.txt
```


### 🔹 Passo 3 – Configurar credenciais da AWS
Certifique-se de ter configurado o AWS CLI corretamente com:

```bash
aws configure
```

### 🔹 Passo 4 – Executar o notebook
Abra o notebook ou script Python que contém o código principal.

- Se estiver usando o AWS SageMaker Studio / Notebook Instance, basta carregar e executar célula por célula.
- Se estiver rodando localmente, garanta que as credenciais AWS estão ativas e que o bucket informado no código realmente exista.
