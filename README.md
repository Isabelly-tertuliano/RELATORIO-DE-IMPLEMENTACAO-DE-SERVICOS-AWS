## RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS
- Data: 2 de junho de 2026
- Empresa: AMMA
- Responsável: Inteligência de Operações e CRM AMMA

## Introdução
  Este relatório apresenta o processo de implementação de ferramentas na empresa AMMA, realizado pela equipe de Inteligência de Operações e CRM. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos, garantindo a sustentabilidade financeira e a eficiência tecnológica para suportar as estratégias de relacionamento da marca.

## Descrição do Projeto
  O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos focados em otimizar a infraestrutura que sustenta a nossa inteligência de dados sem perder a essência acolhedora e humana da marca. A seguir, serão descritas as etapas do projeto:

## Etapa 1:
- Nome da ferramenta: AWS Compute Optimizer
- Foco da ferramenta: Right-sizing (dimensionamento correto e inteligente) de recursos computacionais através de Machine Learning, eliminando o superdimensionamento de servidores.

  Descrição de caso de uso: A AMMA utiliza servidores virtuais para rodar os painéis internos e processar o comportamento diário dos clientes. O AWS Compute Optimizer analisa historicamente esse uso e identifica que os servidores estão operando com folga excessiva ("comprando espaço de garantia desnecessário"). A ferramenta recomenda e automatiza a migração para instâncias menores e de última geração, reduzindo o custo de processamento em até 30% instantaneamente, mantendo a performance das nossas plataformas de monitoramento de forma invisível e fluida.

## Etapa 2:
- Nome da ferramenta: Instâncias EC2 Spot (Amazon EC2 Spot Instances)
- Foco da ferramenta: Processamento de cargas de trabalho flexíveis, tolerantes a falhas e em lote (batch), utilizando capacidade computacional ociosa da AWS com até 90% de desconto.

  Descrição de caso de uso: O nosso Radar de Evasão (Preditivo) precisa rodar algoritmos pesados para cruzar dados de engajamento, histórico de compras e comportamento de toda a base de clientes para classificá-los em Risco Baixo, Médio ou Alto. Essa análise não precisa rodar em tempo real durante o dia; ela pode ser processada de madrugada. Configuramos o Radar de Evasão para rodar exclusivamente em Instâncias EC2 Spot nas janelas de menor movimento da AWS, gerando uma economia massiva no orçamento de dados e garantindo que a inteligência preditiva funcione com custo quase zero.

## Etapa 3:
- Nome da ferramenta: Amazon S3 Intelligent-Tiering
- Foco da ferramenta: Gestão automática e inteligente do ciclo de vida de armazenamento de objetos, movendo arquivos entre camadas de acesso rápido e camadas de arquivos frios/mortos baseando-se no padrão de uso.

  Descrição de caso de uso: A AMMA armazena um grande volume de dados históricos: fotos de campanhas anteriores, logs de navegação antigos, históricos de rituais de beleza e interações de clientes de longo prazo. Manter tudo isso em armazenamento de alta performance é caro. Com o S3 Intelligent-Tiering, se os dados de um cliente inativo (Risco Alto) não são acessados há mais de 30 dias, eles são movidos automaticamente para uma camada de armazenamento muito mais barata (redução de até 68% no custo de armazenamento). No momento em que nossa equipe inicia uma ação direta de resgate humanizado via WhatsApp e o cliente interage, o sistema recupera esses dados históricos de forma imediata e automática para apoiar o atendimento personalizado, sem taxas de recuperação surpresa.

## Conclusão
  A implementação de ferramentas na empresa AMMA tem como esperado a redução imediata do custo operacional de TI, a eliminação do desperdício de infraestrutura ociosa e a automação do ciclo de vida dos nossos dados de CRM, o que aumentará a eficiência e a produtividade da empresa. Ao baratear a sustentação do Radar de Evasão e das Réguas Modulares, garantimos que os investimentos sejam direcionados para o que realmente importa: a experiência e o acolhimento do cliente. Recomenda-se a continuidade da utilização das ferramentas implementadas e a busca por novas tecnologias que possam melhorar ainda mais os processos da empresa, mantendo o respeito ao tempo e à saúde do negócio.

Anexos
Anexo A: Painel de Recomendações do AWS Compute Optimizer (Simulação de Redução de CPU/Memória).

Anexo B: Cronograma de Disparo Noturno do Radar de Evasão via EC2 Spot.

Anexo C: Política de Transição Automática de Camadas de Dados do Amazon S3.

Assinatura do Responsável pelo Projeto:
Isabelly Tertuliano
