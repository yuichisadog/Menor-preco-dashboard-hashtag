# 📊 Dashboard de Análise de Preços - Power BI

## 📌 Visão Geral
Este dashboard foi desenvolvido no **Power BI** para analisar preços e custos de produtos, categorizando os itens mais baratos e as marcas com melhor custo-benefício.

---

## 📊 Principais Métricas e Indicadores
O painel exibe as seguintes informações:

### 🏷️ Produto com Preço Mais Barato
- **Descrição:** Exibe o nome do produto com o menor preço unitário disponível.
- **Métrica:** Identifica o produto com o **menor preço registrado**.

### 💲 Preço Unitário (R$)
- **Descrição:** Mostra o valor do menor preço encontrado no banco de dados.
- **Formato:** Exibido como **R$ X,XX**.

### 🏷️ Produto com Menor Custo
- **Descrição:** Exibe o nome do produto que apresenta o **menor custo** de aquisição.
- **Métrica:** Identifica o produto com o **menor custo unitário**.

### 💲 Custo Unitário (R$)
- **Descrição:** Apresenta o valor do menor custo unitário identificado.
- **Formato:** Exibido como **R$ X,XX**.

### 🎭 Categoria com Menor Preço
- **Descrição:** Mostra a categoria do produto com o **menor preço** registrado.
- **Métrica:** Filtra a categoria do produto associado ao **menor preço**.

### 🎭 Categoria com Menor Custo
- **Descrição:** Apresenta a categoria do produto com o **menor custo de aquisição**.
- **Métrica:** Filtra a categoria do produto associado ao **menor custo**.

### 🏭 Marca com Menor Preço
- **Descrição:** Exibe a marca responsável pelo produto **mais barato** do banco de dados.
- **Métrica:** Identifica a marca associada ao **menor preço**.

### 🏭 Marca com Menor Custo
- **Descrição:** Indica a marca que oferece o **menor custo** no conjunto de produtos analisados.
- **Métrica:** Filtra a marca do produto associado ao **menor custo**.

---

## 🎨 Personalização e Formatação
- **Cores Utilizadas:**
  - 🎨 Fundo: **Tons terrosos** para melhor contraste.
  - 📌 Cabeçalhos: **Vermelho** para destaque das categorias.
  - 🔠 Texto: **Preto** para facilitar a leitura.

- **Formatação dos Valores Monetários:**
  - Todos os valores são exibidos no formato **Real (R$)**.
  - A função `FORMAT()` foi aplicada para garantir a exibição correta da moeda.

---

## ⚙️ Cálculos e DAX Utilizados
Para obter as informações exibidas no dashboard, foram utilizadas as seguintes funções **DAX**:

### 1️⃣ Produto com Menor Preço
```DAX
Produto_Menor_Preco = 
VAR MinPreco = MIN(Tabela[Preco])
RETURN
LOOKUPVALUE(Tabela[Produto], Tabela[Preco], MinPreco)
