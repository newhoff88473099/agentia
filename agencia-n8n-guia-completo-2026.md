# Agência de Automações com N8N - Guia Completo para Dev Solo (2026)

> **Objetivo**: Começar um negócio de automações com N8N de baixo custo, validação rápida, usando lógica CRUD de dev

---

## 📌 Passo 0: O que é N8N e por que vale a pena

**N8N** é uma plataforma de automação open-source (no-code) que conecta aplicativos e cria fluxos de trabalho automáticos [web:11][web:16]:

| Comparação | N8N | Zapier/Make |
|------------|-----|-------------|
| Custo | ~$20/usuário/mês (infra própria) | $200–800/mês [web:29] |
| Execuções | Locais ilimitadas | Limitadas por plano [web:29] |
| Código | Open-source | Fechado [web:29] |
| Para devs | Ideal (APIs, lógica JS) | Menos flexível |

Você paga **só pela hospedagem** (VPS), não por execuções — custo 3x menor que Zapier [web:29].

---

## 🚀 Passo 1: Instalação (1–2 horas, custo inicial ~R$50–100/mês)

### Opção A: VPS com N8N pré-instalado (mais fácil)
- **HostGator**: VPS com N8N instalado (~R$50/mês) [web:11]
- **Hostinger**: VPS + cupom `AESCOLADESITES` (10% off) [web:12][web:14]
- **Cloudfy**: Hospedagem recomendada para N8N + cupons 80% off [web:2]

### Opção B: Instalação manual na VPS (mais barato, ~R$30/mês)
Seguindo tutorial completo [web:11][web:12]:

```bash
# 1. Criar conta gratuita no N8N (cloud) → https://n8n.io/[1][2]
# 2. Acessar VPS (Linux) e instalar:
docker run -it --rm --name n8n -p 5678:5678 n8nio/n8n

# 3. Acessar: http://your-domain:5678
# 4. Criar conta + solicitar licença premium (e-mail)[3]
```

**Variáveis de ambiente recomendadas** [web:12]:

---

## 🛠️ Passo 2: Primeiros Workflows (3–5 dias de prática)

### Conceitos fundamentais [web:11][web:12]:

| Conceito | Função | Exemplo |
|----------|--------|---------|
| **Trigger (Gatilho)** | Inicia o fluxo | Webhook, Cron (tempo), E-mail novo |
| **Fluxo de Dados** | Passa informação entre nodes | JSON entre etapas |
| **Inputs/Outputs** | Entrada e saída de dados | API request → resposta |

---

### WORKFLOW 1: Automação WhatsApp + IA (atendente virtual) [web:12]

**Custo para cliente**: R$ 2.000–5.000 (projeto) + R$ 500–1.500/mês (manutenção) [web:23]

3. Instalar node `n8n-nodes-evolution-api` no N8N [web:12]
4. Criar workflow com trigger webhook + Agent IA
5. Testar com mensagem real

**Prompt para agente IA** [web:12]:

---

### WORKFLOW 2: Excel/Google Sheets + Notificações [web:15]

**Integração Excel/N8N** [web:15]:

**Aplicação para seu nicho**: Automação de relatórios de calibração → quando nova entrada no Excel, gera PDF + envia e-mail ao cliente.

---

### WORKFLOW 3: Monitoramento de Logs QA [web:22][web:28]

**Para controladores de qualidade**:

---

## 💰 Passo 3: Quanto Cobrar (tabelas de 2026)

| Tipo de Serviço | Preço Projeto | Recorrência Mensal |
|-----------------|---------------|-------------------|
| Automação simples (MEI/pequena) | R$ 500–3.125 | R$ 200–500 [web:23] |
| Automação média (empresa) | R$ 3.000–8.000 | R$ 500–1.500 [web:23] |
| Agente IA WhatsApp + CRM | R$ 5.000–10.000 | R$ 1.000–3.000 [web:21] |
| Consultoria por hora | R$ 70–180/h | — [web:23] |

**Rendimentos reais de freelas** [web:26]:
- Iniciantes: US$ 500–1k/mês (~R$ 2.500–5.000)
- Experientes: US$ 3k–8k+ (~R$ 15.000–40.000)
- Agências/produtos: >US$ 10k/mês (~R$ 50.000+)

---

## 🎯 Passo 4: Nichos Ideais para Você (alinhado com suas skills)

### 1. **Laboratórios / Controle de Qualidade** (seu nicho principal!)

**O que automatizar**:
- Relatórios de calibração → Excel → PDF → e-mail automático [web:15]
- Agendamento de equipamentos → WhatsApp + CRM [web:21]
- Monitoramento de logs de testes → Slack/Jira [web:22][web:28]
- Geração de documentos regulatórios → IA + templates [web:20]

**Valor**: R$ 5.000–10.000/projeto + R$ 1.000–2.000/mês

---

### 2. Infoprodutores / Criadores de Conteúdo

**O que automatizar**:
- Captura de leads → WhatsApp → CRM → e-mail marketing [web:21]
- Onboarding de clientes → propostas automática + contrato [web:30]
- Disparos de aulas → Google Sheets + Gmail [web:15]

---

### 3. Empresas Locais (comércio, serviços)

**O que automatizar**:
- Sites com IA + manutenção mensal [web:4]
- Atendimento WhatsApp automático [web:12]
- Relatórios de vendas → Excel + dashboard [web:15]

---

## 📋 Passo 5: Checklist de Validação Rápida (primeiros 30 dias)

| Dia | Ação | Objetivo |
|-----|------|----------|
| 1–2 | Instalar N8N na VPS | Ambiente pronto [web:11][web:12] |
| 3–5 | Criar 3 workflows de prática | Aprender gatilhos + nodes [web:18] |
| 6–10 | Recriar automação WhatsApp + IA | Projeto vendável [web:12] |
| 11–15 | Criar template reutilizável | Produto pronto [web:27] |
| 16–20 | Oferecer para 3–5 empresas locais | Primeiros clientes [web:27] |
| 21–30 | Implementar 1–2 clientes + cobrar | Validação de mercado [web:26] |

**Meta realista mês 1**: 1 cliente @ R$ 3.000–5.000 + R$ 500–1.000/mês [web:23]

---

## 🔧 Passo 6: Melhores Práticas para Workflows Profissionais [web:25]

| Prática | Por que importa |
|---------|---------------|
| **Validação de entradas/saídas** | Evita erros de formato [web:25] |
| **Nodes Try/Catch** | Captura erros + notifica [web:25] |
| **Controle de versões** | Rastreia mudanças [web:25] |
| **Ambiente de teste separado** | Previne bugs no prod [web:25] |
| **Logs + alertas robustos** | Monitoramento constante [web:25] |

---

## 📚 Recursos de Aprendizado

| Tipo | Link | Conteúdo |
|------|------|----------|
| **Curso gratuito** | [web:11] | N8N do zero à automação + agente IA |
| **Tutorial WhatsApp** | [web:12] | Sua primeira automação em 1h |
| **Guide completo** | [web:18] | Passo a passo para iniciantes |
| **Agentes IA** | [web:20] | Como criar agente no N8N |
| **Vender automações** | [web:27] | Guia completo de vendas |

---

## ✅ Resumo: Por que começar com N8N agora?

| Fator | Vantagem |
|-------|----------|
| **Baixo custo** | ~R$ 50–100/mês (vs R$ 1.000+ Zapier) [web:29] |
| **Rápida validação** | 1 cliente em 30 dias possível [web:26] |
| **Usa suas skills** | CRUD + lógica Java/VBA = fácil adaptação [web:16] |
| **Mercado aquecido** | Empresas pagam R$ 5.000–10.000/projeto [web:21] |
| **Recorrência** | R$ 500–3.000/mês por cliente [web:23] |

---

## 📝 Anexos: Scripts e Templates

### Script de Instalação Docker (VPS)
```bash
#!/bin/bash
# install-n8n.sh

docker run -it --rm --name n8n \
  -p 5678:5678 \
  -e WEBHOOK_URL=https://your-domain \
  -e N8N_HOST=$(PRIMARY_DOMAIN) \
  -e GENERIC_TIMEZONE=America/Sao_Paulo \
  -e DB_TYPE=postgresdb \
  n8nio/n8n
```

### Prompt Base para Agent IA (WhatsApp)

---

**Documento gerado em**: Junho 2026  
**Versão**: 1.0  
**Autor**: Guia para Dev Solo (Newton Hoffmann)  
**Local**: Campo Largo, Paraná, BR

---

*Citações: [web:11][web:12][web:14][web:15][web:16][web:17][web:18][web:20][web:21][web:22][web:23][web:25][web:26][web:27][web:28][web:29][web:30]*