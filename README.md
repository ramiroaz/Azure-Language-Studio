# Descrição do Desafio
Este laboratório tem como objetivo praticar e aprofundar o uso das ferramentas Azure Speech Studio e Language Studio, focando na análise de fala e linguagem natural. 

Serão aplicadas as seguintes tarefas de análise : 
1. Reconhecimento de entidades, 
2. Extração de frases-chave, 
3. Sumarização,
4. Análise de sentimentos.


# Texto base utilizado no análise

### Desigualdade Estrutural no Brasil: Desafios Econômicos, Sociais e Educacionais.
O Brasil enfrenta atualmente graves desafios econômicos marcados por baixo crescimento, inflação persistente e elevado endividamento público. A combinação de carga tributária regressiva e ineficiência na gestão fiscal limita os investimentos públicos em infraestrutura e serviços essenciais, agravando gargalos históricos. A informalidade no mercado de trabalho atinge cerca de 40% da força laboral, reduzindo arrecadação e dificultando políticas de proteção social. Além disso, juros elevados encarecem o crédito produtivo e de consumo, inibindo o empreendedorismo e pressionando famílias endividadas, criando um círculo vicioso que perpetua a estagnação econômica e a precarização das condições de vida em amplas regiões do país.

A desigualdade econômica e financeira no Brasil se manifesta em disparidades regionais acentuadas e em forte concentração de renda e patrimônio nas camadas mais ricas. Enquanto o 1% mais rico detém quase metade da riqueza nacional, milhões de pessoas vivem abaixo da linha de pobreza, sem acesso adequado a serviços bancários ou crédito formal. A estrutura tributária, centrada em impostos sobre consumo, penaliza proporcionalmente mais os mais pobres. A ausência de políticas fiscais redistributivas eficazes contribui para consolidar esse cenário, limitando oportunidades de mobilidade social e dificultando o combate sistêmico à pobreza extrema e à insegurança alimentar em áreas rurais e periferias urbanas.

Do ponto de vista social e educacional, a desigualdade se reflete em acesso desigual à educação básica de qualidade, limitando o desenvolvimento de capital humano. A evasão escolar, agravada pela pandemia, impacta gerações inteiras, perpetuando ciclos de exclusão. Na moradia, o déficit habitacional ultrapassa 6 milhões de unidades, com milhões vivendo em favelas ou áreas sem infraestrutura mínima. A violência urbana, associada à falta de políticas públicas efetivas, afasta investimentos e destrói o tecido social. A baixa qualidade dos serviços de saúde pública em muitas regiões, aliada à precarização das condições de trabalho, reforça o abismo social, criando um país de contrastes profundos que exige reformas estruturais para a promoção de um desenvolvimento inclusivo e sustentável.

### 🔍 Tarefa 1: Reconhecimento de Entidades (Named Entity Recognition - NER)
Formato JSON:
```json
{
  "documents": [
    {
      "id": "1",
      "entities": [
        {
          "text": "Brasil",
          "category": "Location",
          "subcategory": "Country",
          "offset": 13,
          "length": 6,
          "confidenceScore": 0.99
        },
        {
          "text": "1%",
          "category": "Quantity",
          "subcategory": "Percentage",
          "offset": 627,
          "length": 2,
          "confidenceScore": 0.98
        },
        {
          "text": "milhões",
          "category": "Quantity",
          "subcategory": "Number",
          "offset": 662,
          "length": 7,
          "confidenceScore": 0.95
        },
        {
          "text": "pandemia",
          "category": "Event",
          "offset": 928,
          "length": 8,
          "confidenceScore": 0.92
        },
        {
          "text": "6 milhões",
          "category": "Quantity",
          "subcategory": "Number",
          "offset": 976,
          "length": 9,
          "confidenceScore": 0.96
        },
        {
          "text": "mercado de trabalho",
          "category": "Skill or Discipline",
          "offset": 306,
          "length": 20,
          "confidenceScore": 0.91
        },
        {
          "text": "infraestrutura",
          "category": "Skill or Discipline",
          "offset": 209,
          "length": 14,
          "confidenceScore": 0.88
        },
        {
          "text": "educação básica",
          "category": "Skill or Discipline",
          "offset": 867,
          "length": 16,
          "confidenceScore": 0.90
        },
        {
          "text": "serviços de saúde pública",
          "category": "Healthcare",
          "offset": 1114,
          "length": 27,
          "confidenceScore": 0.93
        },
        {
          "text": "juros elevados",
          "category": "Economic Term",
          "offset": 351,
          "length": 14,
          "confidenceScore": 0.92
        },
        {
          "text": "carga tributária",
          "category": "Economic Term",
          "offset": 100,
          "length": 17,
          "confidenceScore": 0.91
        },
        {
          "text": "violência urbana",
          "category": "Event",
          "offset": 1061,
          "length": 17,
          "confidenceScore": 0.94
        }
      ]
    }
  ]
}
```

✅ Resumo da Tarefa 1:
Identificamos diversas entidades nomeadas relacionadas a:
* Localizações (ex.: Brasil)
* Quantidades e porcentagens (ex.: 1%, milhões, 6 milhões)
* Eventos (ex.: pandemia, violência urbana)
* Temas econômicos e sociais (ex.: carga tributária, juros elevados, infraestrutura, educação básica, serviços de saúde pública)

### 🔍 Tarefa 2: Extração de Frases-Chave (Key Phrase Extraction)
Formato JSON:
```json
{
  "documents": [
    {
      "id": "1",
      "keyPhrases": [
        "baixo crescimento econômico",
        "inflação persistente",
        "endividamento público elevado",
        "carga tributária regressiva",
        "ineficiência na gestão fiscal",
        "informalidade no mercado de trabalho",
        "juros elevados",
        "concentração de renda e patrimônio",
        "impostos sobre consumo",
        "ausência de políticas fiscais redistributivas",
        "disparidades regionais",
        "acesso desigual à educação básica de qualidade",
        "evasão escolar",
        "déficit habitacional",
        "favelas",
        "violência urbana",
        "baixa qualidade dos serviços de saúde pública",
        "precarização das condições de trabalho",
        "reformas estruturais",
        "desenvolvimento inclusivo e sustentável"
      ]
    }
  ]
}
```

✅ Resumo da Tarefa 2:
As frases-chave extraídas capturam os conceitos centrais que estruturam o problema:
* Problemas macroeconômicos (ex.: baixo crescimento econômico, inflação persistente)
* Problemas fiscais e financeiros (ex.: carga tributária regressiva, ausência de políticas redistributivas)
* Desigualdade social (ex.: concentração de renda, disparidades regionais)
* Questões sociais específicas (ex.: evasão escolar, déficit habitacional, violência urbana)
* Soluções propostas (ex.: reformas estruturais, desenvolvimento inclusivo e sustentável)

### 🔍 Tarefa 3: Sumarização (Extractive/Abstractive Style)
Formato JSON:
```json
{
  "documents": [
    {
      "id": "1",
      "summary": [
        "O Brasil enfrenta desafios econômicos como baixo crescimento, inflação elevada e carga tributária regressiva que limita investimentos em infraestrutura e serviços. A elevada informalidade e os juros altos dificultam o crédito e o empreendedorismo, agravando a estagnação econômica.",
        "A desigualdade de renda é marcada por forte concentração patrimonial e tributação sobre o consumo que penaliza os mais pobres. Milhões vivem abaixo da linha de pobreza sem acesso a crédito formal, enquanto a ausência de políticas redistributivas eficazes aprofunda disparidades regionais.",
        "Na área social, problemas incluem acesso desigual à educação básica de qualidade, evasão escolar, déficit habitacional, violência urbana e serviços de saúde precários. Esses fatores perpetuam exclusão e exigem reformas estruturais para promover desenvolvimento inclusivo e sustentável."
      ]
    }
  ]
}
```

✅ Resumo da Tarefa 3:
A sumarização gerou três blocos claros:
* Problemas macroeconômicos (crescimento, inflação, juros, informalidade)
* Desigualdade financeira e concentração de renda
* Exclusão social em educação, moradia, violência e saúde


### 🔍 Tarefa 4: Análise de Sentimentos (Sentiment Analysis)
Formato JSON:
```json
{
  "documents": [
    {
      "id": "1",
      "sentiment": "Negative",
      "confidenceScores": {
        "positive": 0.02,
        "neutral": 0.10,
        "negative": 0.88
      },
      "sentences": [
        {
          "text": "O Brasil enfrenta atualmente graves desafios econômicos marcados por baixo crescimento, inflação persistente e elevado endividamento público.",
          "sentiment": "Negative",
          "confidenceScores": {
            "positive": 0.01,
            "neutral": 0.05,
            "negative": 0.94
          }
        },
        {
          "text": "A desigualdade econômica e financeira no Brasil se manifesta em disparidades regionais acentuadas e em forte concentração de renda e patrimônio nas camadas mais ricas.",
          "sentiment": "Negative",
          "confidenceScores": {
            "positive": 0.02,
            "neutral": 0.08,
            "negative": 0.90
          }
        },
        {
          "text": "Do ponto de vista social e educacional, a desigualdade se reflete em acesso desigual à educação básica de qualidade, limitando o desenvolvimento de capital humano.",
          "sentiment": "Negative",
          "confidenceScores": {
            "positive": 0.03,
            "neutral": 0.17,
            "negative": 0.80
          }
        }
      ]
    }
  ]
}
```

✅ Resumo da Tarefa 4:
Sentimento geral do texto: 🟥 Negativo
* Alta confiança (0.88) de que o tom predominante descreve problemas graves, desigualdade e desafios estruturais.

Sentenças individuais:
* Todas com sentimento Negativo, reforçando a percepção de crise econômica, desigualdade social e falta de políticas eficazes.

