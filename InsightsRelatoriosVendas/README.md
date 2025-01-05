<h1>
    <a href="https://www.dio.me/">
     <img align="center" width="40px" src="https://hermes.digitalinnovation.one/assets/diome/logo-minimized.png"></a>
    <span>Microsoft AI for Tech – Criando Prompts Inteligentes</span>
</h1>

# :computer: Desafio de projeto: Utilizando Prompts para Gerar Insights de Relatórios de Vendas

Analisar a tabela de vendas de produtos de uma fábrica vendido por 3 diferentes sites, sendo os dados brutos um arquivo por site em `data/`  

# :bulb: Solução do desafio

A análise de dados completa está no arquivo `data_process.ipynb` Combinei as 3 tabelas em um dataframe utilizando pandas:

```python
# Importando os dados
data = []

for file in os.listdir('./data'):
    if file.endswith('.csv'):
        data.append(pd.read_csv('./data/' + file))
        print(file)

# Combinando os dados em um único dataframe
combined_data = pd.concat(data, ignore_index=True)
```

## Verifiquei se haviam dados nulos:

```python
# Checando se há nulos
combined_data.info()
```
```console
RangeIndex: 60 entries, 0 to 59
Data columns (total 14 columns):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   SKU               60 non-null     object 
 1   product_sold      60 non-null     object 
 2   date              60 non-null     object 
 3   quantity          60 non-null     int64  
 4   unit_price        60 non-null     int64  
 5   total_price       60 non-null     int64  
 6   currency          60 non-null     object 
 7   site              60 non-null     object 
 8   discount_coupon   60 non-null     object 
 9   discount_value    60 non-null     float64
 10  buyer_birth_date  60 non-null     object 
 11  buyer_name        60 non-null     object 
 12  delivery_country  60 non-null     object 
 13  invoice_id        60 non-null     object 
```

## Removi as colunas desnecessárias para análise:

```python
# Removendo colunas desnecessárias parra análise
combined_data = combined_data.drop(columns=['SKU', 'discount_coupon', 'buyer_name', 'invoice_id'])
```

## Calculei a idade aproximada dos compradores:

```python
# Calculando a idade dos compradores
combined_data['buyer_age'] = combined_data['date'].dt.year - combined_data['buyer_birth_date'].dt.year
```

## Observei alguns dados agrupados:

```python
# Quantidade de vendas por site
combined_data.groupby(['site'])['quantity'].sum()
```
```console
site
AliExpress    58
Etsy          56
Shopee        64
Name: quantity, dtype: int64
```
```python
# Quantidade de Produtos vendidos
combined_data.groupby(['product_sold'])['quantity'].sum()
```
```console
product_sold
MEGANIUM RG353M           29
NEW MEGANIUM RG 40XXV     41
NEW MEGANIUM RG CubeXX    36
NEW MEGANIUM RG28XX       36
NEW MEGANIUM RG35XX       36
Name: quantity, dtype: int64
```
```python
# Média de idade comprador por país
combined_data.groupby(['delivery_country'])['buyer_age'].mean().round(0).astype(int)
```
```console
delivery_country
Australia    44
Canada       36
France       43
Germany      43
Japan        44
UK           44
USA          38
Name: buyer_age, dtype: int64
```

## Salvando os dados processados em arquivo csv:

```python
# Salvando csv
combined_data.to_csv('processed_data.csv', index=False)
```

# Insight dos dados com ChatGPT

No notebook de processamento de dados tentei usar a API do Gemini para analisar o dataframe, porém tive que converter a tabela para markdown e a resposta retornada estava errada. Utilizando a tabela em markdown com o chatgpt também retornou dados errados. Então utilizei o arquivo `processed_data.csv` parra obter resultados satisfatórios com o chatGPPT gratuito.

## Prompt

```prompt
Analise o seguinte relatório de vendas:

- Identifique os 3 produtos mais vendidos. 
- Retorne a quantidade de produtos vendidos por site.
- Retorne uma tabela agrupada com produtos vendidos,  país e soma da quantidade vendida.
- Retorne a média da idade dos compradores  por país. 
```

## Resposta



O arquivo contém 60 registros com 11 colunas, incluindo informações sobre produtos vendidos, datas, quantidades, preços, site de venda, país de entrega e dados dos compradores. Vamos realizar as análises solicitadas.

### Passos:
1. **Identificar os 3 produtos mais vendidos.**
2. **Calcular a quantidade de produtos vendidos por site.**
3. **Gerar uma tabela agrupada com produtos vendidos, país e soma da quantidade vendida.**
4. **Calcular a média da idade dos compradores por país.**

Vou processar essas análises.

### Resultados da Análise:

1. **3 Produtos Mais Vendidos**:
   - **NEW MEGANIUM RG 40XXV**: 41 unidades
   - **NEW MEGANIUM RG CubeXX**: 36 unidades
   - **NEW MEGANIUM RG28XX**: 36 unidades

2. **Quantidade de Produtos Vendidos por Site**:
   - Shopee: 64 unidades
   - AliExpress: 58 unidades
   - Etsy: 56 unidades

3. **Tabela Agrupada de Produtos Vendidos por País**:
   (Exemplo de algumas entradas)
   - MEGANIUM RG353M - Austrália: 5 unidades
   - NEW MEGANIUM RG 40XXV - Canadá: 19 unidades
   - NEW MEGANIUM RG CubeXX - França: 9 unidades

4. **Média da Idade dos Compradores por País**:
   - Austrália: 43.89 anos
   - Canadá: 35.57 anos
   - França: 43.25 anos
   - Japão: 43.88 anos
   - EUA: 38.33 anos

Se precisar de detalhes adicionais ou ajustes, é só pedir! 😊

## O limite da conta gratuita se esgotou rapidamente:
```consoel
retorne uma tabela com quantidade de produtos vendidos, por produto por país
```

    It seems like I can’t do more advanced data analysis right now. Please try again later. If you'd like, I can 
    guide you on how to analyze the data on your own using a tool like Python 
    or Excel. Let me know how you'd like to proceed! ​​

**Você chegou ao seu limite de análise de dados.**

Faça upgrade para o ChatGPT Plus ou tente novamente amanhã após 18:33.