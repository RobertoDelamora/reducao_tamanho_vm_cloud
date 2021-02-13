# Recomendação de redução de tamanho de VMs na cloud pública

**A proposta desse trabalho é implementar um modelo descritivo que permita avaliar de forma abrangente e rápida o consumo de cpu de servidores IaaS e recomendar possibilidades de redução nos tamanhos das máquinas, sem que ocorra perda de performance significativa e com redução de custos.**


### Roteiro Básico:

#### Descrição do processo:
• Análise realizada em ambiente de nuvem da Microsoft Azure;

• Uso de informações sobre o consumo de cpu dos servidores, coletadas previamente por outro processo e armazenadas em banco de dados;

• Uso de tabela adicional com informações de todas as famílias e tamanhos de VMs IaaS disponíveis no catálogo da Azure;

• Análise estatística dos dados e apresentação de gráficos de comportamento;

• Cálculo de opções e impactos na redução do número de cpus;

• Formulação da recomendação;

• Apresentação de resultados com lista de servidores que possuem recomendação. Só aparecem na lista as VMs que receberam algum tipo de recomendação.


#### Parâmetros básicos:
• Ambiente da amostra: servidores virtuais (VMs) IaaS;

• Período de análise dos dados: 7 dias anteriores à coleta;

• Uso de métricas estatísticas (Média, Mínimo, Máximo, Desvio Padrão, Percentil 95) para avaliação matemática do consumo;

• Uso de métrica adicional como valor de corte (3sigma), que considera uma folga operacional;

• Limite de consumo operacional ("threshold") definido em 80%;

• Variável new_3sigma é o valor estimado como limite de operação para a nova VM ajustada. Pela regra ele não pode ser maior que 80%.


#### Premissas:
• A análise considera somente o consumo de cpu como parâmetro principal;

• A recomendação é feita sempre dentro da mesma família/série de tamanhos;

• São excluídos do processo:

-Servidores com 1 cpu (não tem como reduzir mais que isso);

-Servidores com 3sigma > 35% (com a redução, a nova VM ficaria fora do limite operacional de consumo de 80%);

-Servidores com 3sigma igual a zero (não houve uso da VM no período analisado);





**Importante:** Os dados apresentados foram anonimizados por questões de segurança e privacidade.

# Follow me at Linkedin

https://www.linkedin.com/in/robertodelamora/
