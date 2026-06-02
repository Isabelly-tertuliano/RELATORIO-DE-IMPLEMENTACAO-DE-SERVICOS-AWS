# **Cronograma de Disparo Noturno do Radar de Evasão via EC2 Spot**

**Ref: Orquestração e Automação de Cargas de Trabalho Flexíveis**

Para evitar o custo de manter servidores de processamento de dados ligados 24 horas por dia, a rotina do **Radar de Evasão Preditivo** foi desenhada para operar em lote (*batch processing*) durante a madrugada, utilizando a capacidade ociosa da AWS (Instâncias Spot).

### **Arquitetura do Fluxo de Trabalho**

\[01:00 AM\] Trigger temporal (Amazon EventBridge)  
   │  
   ▼  
\[01:05 AM\] Requisição de Instância EC2 Spot (Preço até 90% menor)  
   │  
   ▼  
\[01:10 AM\] Download seguro dos dados de engajamento da base AMMA  
   │  
   ▼  
\[01:15 AM \- 03:30 AM\] Processamento dos Modelos Preditivos (Risco Baixo, Médio, Alto)  
   │  
   ▼  
\[03:45 AM\] Atualização das Réguas Modulares no HubSpot / Hyperflow  
   │  
   ▼  
\[04:00 AM\] Desligamento e encerramento automático da Instância Spot

### **Plano de Contingência para Interrupções (Resiliência Spot)**

Caso a AWS precise recuperar a capacidade computacional devido a um pico de demanda global, o sistema segue o seguinte protocolo automatizado:

1. **Aviso de Interrupção:** O sistema recebe um alerta prévio de 2 minutos da AWS.  
2. **Salvamento de Estado (*Checkpointing*):** O algoritmo interrompe o processamento na última linha calculada e salva o progresso atual no Amazon S3.  
3. **Retomada Automática:** O script aguarda uma nova vaga de Instância Spot disponível ou, caso seja uma noite de extrema urgência, aciona uma instância On-Demand convencional apenas para finalizar o lote restante, garantindo que a equipe de CRM tenha a base atualizada antes do início do horário comercial.