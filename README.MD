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

## ☁️ Execução do Projeto
🔹 Passo 1 – Clonar o repositório

```bash
git clone https://github.com/seu-usuario/nome-do-repo.git
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

---

## 🎬 Demonstração Audiovisual 

[Clique aqui para assistir à demonstração do projeto no Google Drive](https://drive.google.com/file/d/1rXv5gQ5XgmR6jZI8Oanh9GXU_hzcDpY6/view?usp=sharing)

---

👨‍💻 Autor
Desenvolvido por Luan Natan de Sousa 🚀