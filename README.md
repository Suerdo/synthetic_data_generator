#  Geração de Dados Sintéticos para Preservação de Privacidade

Este projeto tem como objetivo gerar dados sintéticos realistas para ambientes de desenvolvimento, teste e análise, garantindo a privacidade dos dados pessoais, em conformidade com a **LGPD** e outras regulamentações de proteção de dados. A proposta é preservar os padrões estatísticos dos dados reais sem expor informações sensíveis.

---

## Explicação do Problema

A utilização de dados reais em ambientes de desenvolvimento e pesquisa esbarra em questões legais e éticas. No Brasil, órgãos públicos impõem restrições severas quanto ao uso de informações pessoais como CPF, RG, entre outros. Para contornar essa limitação, a geração de **dados sintéticos** surge como alternativa, desde que:

- Reproduzam padrões estatísticos dos dados originais.
- Garantam o anonimato total dos registros.
- Evitem riscos de vazamento e reidentificação.

---

##  Dataset Utilizado e Exploração

Foi utilizada a biblioteca **[Faker](https://faker.readthedocs.io/en/master/)** para gerar dados de treinamento fictícios. Os dados incluem:

- Nomes
- Endereços
- CPF e RG (formatados)
- Outras informações típicas de bases reais

Esses dados permitem criar ambientes de teste que simulam contextos reais, sem comprometer a privacidade.

---

## Modelo Utilizado: CTGAN (Conditional Tabular GAN)

Para a geração dos dados sintéticos, foi adotado o **[CTGAN](https://github.com/sdv-dev/CTGAN)**, uma abordagem baseada em redes adversariais generativas condicionais, desenvolvida especialmente para lidar com:

- Dados tabulares complexos
- Variáveis categóricas e desbalanceadas
- Distribuições não-lineares e multivariadas

### Por que o CTGAN?
- Preserva as **correlações estatísticas** entre as variáveis.
- Gera dados sintéticos com alta fidelidade.
- Lida melhor com dados desbalanceados que métodos tradicionais.

---

## Resultados

As análises mostraram resultados satisfatórios:

- A sobreposição parcial das nuvens de pontos no **PCA** confirma que o modelo capturou a estrutura multivariada dos dados originais.
- A análise **t-SNE** evidenciou a capacidade do modelo em replicar relações não-lineares entre atributos.
- Os dados gerados mantêm a utilidade prática e a coerência estatística, sem comprometer a privacidade.

---

## Como Usar

### Pré-requisitos

Certifique-se de ter o Python 3.8+ instalado, além das bibliotecas necessárias:

```bash
pip install sdv faker pandas scikit-learn matplotlib seaborn
```

## 📎 Referências

- [Faker — Documentação Oficial](https://faker.readthedocs.io/en/master/)
- [CTGAN — GitHub Oficial](https://github.com/sdv-dev/CTGAN)
