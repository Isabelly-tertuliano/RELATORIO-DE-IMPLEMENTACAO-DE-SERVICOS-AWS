# **Política de Transição Automática de Camadas de Dados do Amazon S3**

**Ref: Ciclo de Vida de Dados e Otimização de Armazenamento**

Os dados e arquivos da AMMA são categorizados automaticamente de acordo com a frequência de acesso, garantindo que o histórico de clientes inativos ou campanhas passadas não gerem custos desnecessários, mas continuem disponíveis instantaneamente para o resgate humanizado.

### **Matriz de Transição do S3 Intelligent-Tiering**

| Camada de Armazenamento | Critério de Movimentação | Custo Relativo | Tempo de Acesso | Tipo de Dado Armazenado |
| :---- | :---- | :---- | :---- | :---- |
| **Frequent Access Tier** | Padrão de entrada (0 a 30 dias sem alteração). | 100% (Base) | Milissegundos | Dados de clientes ativos (Risco Baixo), compras recentes e artes da campanha atual. |
| **Infrequent Access Tier** | Automático após 30 dias consecutivos de inatividade. | \~60% do valor base | Milissegundos | Histórico de rituais e compras de clientes em Risco Médio. |
| **Archive Instant Access** | Automático após 90 dias consecutivos de inatividade. | \~32% do valor base | Milissegundos | Logs antigos de navegação, fotos de campanhas de anos anteriores e dados de clientes em Risco Alto (Inativos). |

### 

### **Fluxo de Recuperação Automática (*Resgate Humano*)**

Quando o sistema de CRM detecta um retorno de engajamento ou quando a atendente de WhatsApp aciona o perfil de um cliente que estava na camada **Archive Instant Access**:

* O primeiro clique na ficha do cliente dispara uma requisição de leitura ao Amazon S3.  
* O dado é lido instantaneamente (em milissegundos) e, de forma automática, o S3 Intelligent-Tiering move esse cliente de volta para a camada **Frequent Access Tier**.  
* **Custo de recuperação:** US$ 0,00 (Diferente dos sistemas de arquivos mortos tradicionais, o Intelligent-Tiering não cobra taxa por resgate ou leitura de dados frios).

