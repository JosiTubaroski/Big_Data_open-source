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
   - 
