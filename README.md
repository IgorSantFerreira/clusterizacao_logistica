# Clusterização logística com K-Means

**Python · Pandas · Scikit-learn · Plotly**

Projeto acadêmico de Ciência de Dados desenvolvido na FIAP. A proposta é analisar entregas malsucedidas de um e-commerce fictício e identificar regiões candidatas à instalação de centros automatizados de retirada.

## Problema e abordagem

A base contém latitude, longitude e valor de cada entrega. O objetivo não é prever o valor das compras: é **agrupar entregas próximas** e depois medir o volume financeiro associado a cada região.

O que fiz:

- Tratei os campos numéricos e conferi valores ausentes e registros duplicados, preservando o CSV original.
- Usei **latitude e longitude** como entrada do K-Means. O valor da entrega ficou de fora para não influenciar a distância entre pontos.
- Comparei **K de 2 a 10** usando Inércia (Método do Cotovelo) e Índice de Silhueta.
- Calculei centroides, quantidade de entregas, valor total e ticket médio de cada cluster.
- Visualizei a distribuição e os resultados em gráficos com Plotly.

## Resultados

| Indicador | Resultado |
| --- | ---: |
| Entregas analisadas | 653 |
| K selecionado | 2 |
| Índice de Silhueta | 0,4703 |
| Valor total das entregas | R$ 41.183,81 |

| Cluster | Entregas | Valor total |
| --- | ---: | ---: |
| 1 | 335 | R$ 20.890,95 |
| 2 | 318 | R$ 20.292,86 |

**Decisão:** entre os valores testados, K=2 apresentou a maior Silhueta. É uma proposta inicial de duas regiões de atendimento, **não uma conclusão de que dois centros seriam a solução economicamente ideal**.

## Como executar

1. Abra [`clusterizacao_logistica.ipynb`](./clusterizacao_logistica.ipynb) no VS Code ou Jupyter.
2. O notebook instala as dependências na primeira célula de código.
3. Na leitura do CSV, use o nome publicado neste repositório: `geolocalizacao_dataset.csv` (o notebook ainda referencia o nome original do arquivo fornecido na atividade).
4. Execute as células em sequência. Os gráficos Plotly e os resumos são gerados no próprio notebook.

## Limitações

As coordenadas são fictícias. O estudo não considera rotas reais, tempo de deslocamento, custo de instalação, capacidade dos pontos de retirada nem adesão dos clientes. A soma dos valores das entregas representa **volume financeiro atendido**, não economia comprovada.

**Autor:** Igor Santana Ferreira · [igor.sant.ferreira@gmail.com](mailto:igor.sant.ferreira@gmail.com)
