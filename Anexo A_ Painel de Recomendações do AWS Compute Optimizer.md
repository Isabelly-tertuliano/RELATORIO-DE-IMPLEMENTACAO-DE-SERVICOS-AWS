# **Painel de Recomendações do AWS Compute Optimizer**

**Ref: Otimização de Infraestrutura do Monitoramento de CRM**

O AWS Compute Optimizer analisou o comportamento das instâncias de computação que sustentam a plataforma interna da AMMA durante um período de 14 dias. A análise identificou um cenário clássico de **superdimensionamento** (recursos contratados acima da necessidade real).

### **Diagnóstico da Infraestrutura Atual**

* **Instância Atual:** m5.xlarge (4 vCPUs, 16 GiB RAM)  
* **Utilização Média de CPU:** 12%  
* **Pico Máximo de CPU:** 28%  
* **Status detectado:** *Over-provisioned* (Superdimensionada)

### **Recomendação de Redimensionamento (*Right-sizing*)**

A ferramenta recomendou a migração para uma instância de nova geração, mais eficiente e com tamanho adequado à carga real de trabalho da AMMA.

| Métrica | Cenário Atual (m5.xlarge) | Cenário Recomendado (t4g.medium) | Impacto / Alteração |
| :---- | :---- | :---- | :---- |
| **Arquitetura** | Intel x86 | AWS Graviton2 (ARM) | Maior eficiência por Watt |
| **Capacidade** | 4 vCPUs / 16 GiB | 2 vCPUs / 4 GiB | Ajustado à carga real |
| **Custo Mensal Estimado** | US$ 138,70 | US$ 24,09 | **Economia de \~82,6%** |

**Nota de Implementação:** A migração para a família t4g (processadores Graviton) mantém a estabilidade dos painéis de CRM da AMMA e reduz drasticamente o custo fixo, liberando orçamento para as ações de relacionamento.

