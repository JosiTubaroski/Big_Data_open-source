<div> 
<p><a href="https://github.com/JosiTubaroski/Introducao_Engenharia_Dados/blob/main/README.md">Introdução a Engenharia de Dados</a></p>
</div> 

# Caso de uso prático de processamento de dados de um grande big data utilizando as ferramentas Open Source.

Aqui está um caso prático de processamento de Big Data utilizando ferramentas open-source:

## Cenário: Análise de Sentimentos em Redes Sociais

- Objetivo: Processar e analisar grandes volumes de dados extraídos de redes sociais para identificar tendências e sentimentos sobre produtos e serviços.

## Arquitetura Geral com Ferramentas Open-Source

1. Coleta de Dados: Apache Kafka
   - O Apache Kafka será usado para coletar e transmitir dados de redes sociais em tempo real.
   - Conectores Kafka (como Kafka Connect) podem ser usados para integrar APIs de redes sociais, como Twitter.
  
2. Processamento em Tempo Real: Apache Flink
   - O Apache Flink processará os dados transmitidos pelo Kafka.
   - Ele executará transformações, como extração de texto, remoção de stopwords, e cálculo de pontuações de sentimentos em tempo real.
  
3. Armazenamento de Dados Processados: Apache Cassandra
   - Os resultados processados serão armazenados no banco NoSQL Apache Cassandra, otimizando consultas de leitura para análises futuras.
  
4. Análise de Dados em Lote: Apache Spark
   - Para análises mais aprofundadas, os dados brutos armazenados podem ser processados por lotes usando Apache Spark.
  
5. Visualização de Dados: Grafana
   - Um painel no Grafana apresentará visualizações como:
     - Gráficos de sentimentos ao longo do tempo.
     - Palavras mais mencionadas (Word Cloud).
     - Análises geográficas dos tweets.

## Fluxo de Trabalho Detalhado 

1. Coleta de Dados com Apache Kafka

- Configuração:
  - Use um conector Kafka para consumir dados do Twitter Streaming API.
  - Configure um tópico Kafka para cada tipo de dado (por exemplo, tweets, retweets).

2. Processamento em Tempo Real com Apache Flink
   - Tarefas de Flink:
     - Conectar-se ao tópico Kafka.
     - Limpar os dados: Remover tweets duplicados e fazer parsing do JSON.
     - Analisar o sentimento: Usar uma biblioteca como NLTK ou TextBlob para atribuir um valor de sentimento (positivo, neutro, negativo).
     - Produzir os resultados: Gravar os resultados processados em um novo tópico Kafka.

3. Armazenamento no Apache Cassandra
   - Estrutura de Tabelas:
     - Crie tabelas com colunas como:
       - tweet_id
       - timestamp
       - sentiment_score
       - location
       - processed_text
    - Insira os resultados processados do Flink em Cassandra.

4. Processamento em Lote com Apache Spark
   - Tarefas de Spark:
     - Extraia dados brutos de Cassandra ou de um Data Lake (como HDFS ou MinIO).
     - Realize análises agregadas, como:
       - Sentimentos médios por localização.
       - Palavras mais frequentemente associadas a sentimentos negativos.

5. Visualização com Grafana
   - Conecte o Grafana ao Cassandra ou ao Spark Structured Streaming.
   - Crie dashboards para monitorar:
     - Tendências de sentimento ao longo do tempo.
     - Mapas de calor baseados em localização.
     - Distribuições de sentimentos por hashtags ou tópicos.

### Exemplo de Código (Processamento com Apache Flink)
)
