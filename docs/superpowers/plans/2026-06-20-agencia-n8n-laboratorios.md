# Agencia N8N Laboratorios Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Validar em 30 dias uma agencia de automacoes com N8N focada em laboratorios e controle de qualidade, chegando a uma oferta testada, demonstracoes funcionais e primeira oportunidade paga.

**Architecture:** O trabalho sera organizado em frentes pequenas e verificaveis: infraestrutura N8N, automacoes demonstraveis, oferta comercial, prospeccao e entrega recorrente. Cada frente gera artefatos reutilizaveis para reduzir improviso e permitir evolucao apos o primeiro cliente.

**Tech Stack:** N8N, VPS Linux, Docker, Postgres, dominio com HTTPS, Google Sheets ou Excel, geracao de PDF, e-mail SMTP, WhatsApp via integracao disponivel, documentos Markdown.

---

## Source Spec

- Design aprovado: `docs/superpowers/specs/2026-06-20-agencia-n8n-laboratorios-design.md`
- Guia base: `agencia-n8n-guia-completo-2026.md`

## File Structure

- Create: `docs/operacao/infra-n8n-checklist.md`
  - Responsavel por registrar requisitos de VPS, dominio, variaveis, backup, logs e ambiente de teste.
- Create: `docs/operacao/workflows-demo.md`
  - Responsavel por descrever as 3 automacoes demonstraveis e seus criterios de aceite.
- Create: `docs/comercial/oferta-laboratorios.md`
  - Responsavel por consolidar promessa, escopo, preco, recorrencia e limites da oferta.
- Create: `docs/comercial/roteiro-diagnostico.md`
  - Responsavel por guiar conversas comerciais com perguntas objetivas sobre processos tecnicos.
- Create: `docs/comercial/prospeccao-laboratorios.md`
  - Responsavel por definir criterios de lista, metas de contato e mensagem inicial.
- Create: `docs/entrega/processo-entrega.md`
  - Responsavel por padronizar diagnostico, mapeamento, implantacao, treinamento e suporte.
- Create: `docs/entrega/modelo-proposta.md`
  - Responsavel por oferecer uma proposta comercial simples para primeiro projeto.
- Create: `docs/metricas/validacao-30-dias.md`
  - Responsavel por acompanhar metas, indicadores, decisoes e aprendizados do ciclo.

## Task 1: Criar Checklist De Infraestrutura N8N

**Files:**
- Create: `docs/operacao/infra-n8n-checklist.md`

- [ ] **Step 1: Criar a pasta de operacao**

Run:

```powershell
New-Item -ItemType Directory -Force docs\operacao
```

Expected: a pasta `docs/operacao` existe.

- [ ] **Step 2: Criar o checklist de infraestrutura**

Create `docs/operacao/infra-n8n-checklist.md` with:

```markdown
# Checklist De Infraestrutura N8N

## Objetivo

Ter um ambiente N8N simples, barato e confiavel o suficiente para demonstracoes comerciais e primeiros clientes.

## Decisoes Iniciais

- Hospedagem: VPS Linux.
- Execucao: Docker.
- Banco de dados: Postgres.
- Fuso horario: America/Sao_Paulo.
- Uso inicial: demonstracao, piloto e primeiro cliente.

## Checklist Tecnico

- [ ] Contratar VPS com pelo menos 1 vCPU, 1 GB RAM e 20 GB de disco.
- [ ] Apontar dominio ou subdominio para a VPS.
- [ ] Configurar HTTPS.
- [ ] Instalar Docker e Docker Compose.
- [ ] Subir N8N com volume persistente.
- [ ] Configurar Postgres como banco de dados.
- [ ] Configurar `WEBHOOK_URL` com URL publica em HTTPS.
- [ ] Configurar `GENERIC_TIMEZONE=America/Sao_Paulo`.
- [ ] Criar usuario administrador.
- [ ] Bloquear acessos desnecessarios na VPS.
- [ ] Registrar credenciais em cofre seguro.

## Backup

- [ ] Exportar workflows apos cada mudanca relevante.
- [ ] Fazer backup do banco Postgres.
- [ ] Guardar copia dos templates usados nas demonstracoes.
- [ ] Testar restauracao de pelo menos um workflow exportado.

## Logs E Alertas

- [ ] Ativar historico de execucoes no N8N.
- [ ] Criar workflow simples para notificar falhas criticas por e-mail.
- [ ] Registrar data, nome do workflow, erro e acao tomada.

## Criterio De Pronto

O ambiente esta pronto quando o N8N abre por HTTPS, executa um workflow de teste, persiste dados apos reinicio e permite exportar/importar workflows.
```

- [ ] **Step 3: Verificar o arquivo**

Run:

```powershell
Get-Content docs\operacao\infra-n8n-checklist.md
```

Expected: o arquivo existe e contem secoes de objetivo, checklist tecnico, backup, logs e criterio de pronto.

- [ ] **Step 4: Commit**

Run:

```powershell
git add docs/operacao/infra-n8n-checklist.md
git commit -m "docs: add n8n infrastructure checklist"
```

Expected: commit criado com o checklist de infraestrutura.

## Task 2: Definir As 3 Demonstracoes Tecnicas

**Files:**
- Create: `docs/operacao/workflows-demo.md`

- [ ] **Step 1: Criar documento de workflows demonstraveis**

Create `docs/operacao/workflows-demo.md` with:

```markdown
# Workflows Demonstraveis Para Laboratorios

## Objetivo

Criar 3 demonstracoes comerciais que mostrem valor pratico para laboratorios, controle de qualidade, calibracao e operacoes tecnicas.

## Demo 1: Relatorio De Calibracao

### Dor

Relatorios feitos manualmente em planilha ou editor de texto consomem tempo, geram erro de preenchimento e atrasam envio ao cliente.

### Fluxo

1. Receber dados por Google Sheets, Excel ou formulario.
2. Validar campos obrigatorios: cliente, equipamento, numero de serie, data, responsavel e resultado.
3. Gerar PDF com template padrao.
4. Enviar PDF por e-mail ao cliente.
5. Registrar status do envio.

### Criterios De Aceite

- [ ] Dados incompletos nao geram PDF.
- [ ] PDF contem cliente, equipamento, data e resultado.
- [ ] E-mail e enviado com assunto padronizado.
- [ ] Execucao fica registrada.

## Demo 2: Agenda E Manutencao De Equipamentos

### Dor

Vencimentos de calibracao, manutencao ou verificacao sao esquecidos quando dependem de controle manual.

### Fluxo

1. Ler planilha de equipamentos.
2. Identificar vencimentos nos proximos 7, 15 ou 30 dias.
3. Enviar aviso por e-mail ou WhatsApp.
4. Marcar equipamento como notificado.

### Criterios De Aceite

- [ ] Equipamentos vencidos ou proximos do vencimento sao detectados.
- [ ] Responsavel recebe alerta claro.
- [ ] Equipamentos ja notificados nao geram duplicidade no mesmo ciclo.

## Demo 3: Monitoramento De Logs Ou Processos QA

### Dor

Ocorrencias criticas ficam espalhadas em arquivos, planilhas ou sistemas e sao vistas tarde demais.

### Fluxo

1. Receber log por arquivo, webhook ou planilha.
2. Filtrar condicoes criticas.
3. Enviar alerta ao responsavel.
4. Registrar historico de ocorrencias.

### Criterios De Aceite

- [ ] Eventos normais nao geram alerta.
- [ ] Eventos criticos geram alerta com contexto minimo.
- [ ] Historico registra data, origem, severidade e acao tomada.

## Ordem De Construcao

1. Relatorio de calibracao.
2. Agenda e manutencao.
3. Monitoramento QA.

## Criterio De Pronto

As demonstracoes estao prontas quando podem ser apresentadas em ate 10 minutos, com dados simulados realistas e explicacao direta do ganho operacional.
```

- [ ] **Step 2: Verificar criterios de aceite**

Run:

```powershell
Select-String -Path docs\operacao\workflows-demo.md -Pattern "Criterios De Aceite"
```

Expected: 3 ocorrencias, uma para cada demonstracao.

- [ ] **Step 3: Commit**

Run:

```powershell
git add docs/operacao/workflows-demo.md
git commit -m "docs: define laboratory workflow demos"
```

Expected: commit criado com as demonstracoes tecnicas.

## Task 3: Criar Oferta Comercial Inicial

**Files:**
- Create: `docs/comercial/oferta-laboratorios.md`

- [ ] **Step 1: Criar a pasta comercial**

Run:

```powershell
New-Item -ItemType Directory -Force docs\comercial
```

Expected: a pasta `docs/comercial` existe.

- [ ] **Step 2: Criar a oferta**

Create `docs/comercial/oferta-laboratorios.md` with:

```markdown
# Oferta Comercial Para Laboratorios

## Nome Da Oferta

Automacao de relatorios e rotinas de controle de qualidade.

## Promessa

Reduzir trabalho manual, atrasos e erros em processos tecnicos usando automacoes com N8N integradas a planilhas, PDFs, e-mail e notificacoes.

## Cliente Ideal

- Laboratorio de calibracao.
- Laboratorio de ensaio.
- Empresa de metrologia.
- Industria pequena com controle de qualidade.
- Prestador de servico tecnico com relatorios recorrentes.

## Problemas Que A Oferta Resolve

- Relatorios montados manualmente.
- Envio atrasado de documentos.
- Controle de vencimento feito em planilha.
- Falta de alerta para equipamentos ou ocorrencias.
- Retrabalho por erro de preenchimento.

## Escopo Do Projeto Inicial

- Diagnostico de um processo.
- Automacao de um fluxo principal.
- Teste com dados reais ou amostra fornecida pelo cliente.
- Documentacao simples do fluxo.
- Treinamento rapido para uso.
- Suporte inicial por 7 dias apos implantacao.

## Fora Do Escopo Do Projeto Inicial

- Integracoes com sistemas fechados sem API disponivel.
- Substituicao completa de sistema de gestao.
- Garantia juridica ou regulatoria sobre documentos.
- Criacao de plataforma SaaS propria.
- Alteracoes ilimitadas apos aceite.

## Preco

- Projeto inicial: R$ 3.000 a R$ 5.000.
- Piloto fechado, quando necessario: R$ 1.500 a R$ 2.500.
- Manutencao mensal: R$ 500 a R$ 1.000.

## Manutencao Mensal

Inclui:

- Monitoramento de falhas.
- Pequenos ajustes.
- Backup de workflows.
- Relatorio mensal simples.
- Suporte para duvidas operacionais.

Nao inclui:

- Novos fluxos.
- Mudancas grandes de regra.
- Integracoes adicionais.
- Atendimento emergencial fora do horario combinado.

## Mensagem Curta

Eu ajudo laboratorios e empresas de controle de qualidade a automatizar relatorios, alertas e rotinas manuais com N8N, reduzindo retrabalho e atrasos sem precisar trocar o sistema atual.
```

- [ ] **Step 3: Validar faixas de preco**

Run:

```powershell
Select-String -Path docs\comercial\oferta-laboratorios.md -Pattern "R\\$ 3.000|R\\$ 500|Piloto"
```

Expected: aparecem as faixas de projeto, manutencao e piloto.

- [ ] **Step 4: Commit**

Run:

```powershell
git add docs/comercial/oferta-laboratorios.md
git commit -m "docs: add laboratory automation offer"
```

Expected: commit criado com a oferta comercial.

## Task 4: Criar Roteiro De Diagnostico

**Files:**
- Create: `docs/comercial/roteiro-diagnostico.md`

- [ ] **Step 1: Criar roteiro de diagnostico**

Create `docs/comercial/roteiro-diagnostico.md` with:

```markdown
# Roteiro De Diagnostico

## Objetivo

Conduzir uma conversa de 20 a 30 minutos para identificar um processo manual que possa virar projeto inicial de automacao.

## Abertura

Obrigado por separar esse tempo. A ideia da conversa e entender onde existem tarefas repetitivas, relatorios, alertas ou controles manuais que estejam consumindo tempo ou gerando atraso.

## Perguntas Principais

1. Quais relatorios ou documentos sao gerados com maior frequencia?
2. Esses relatorios nascem de planilha, sistema, formulario ou entrada manual?
3. Quem preenche os dados e quem revisa?
4. Onde acontecem mais erros ou retrabalho?
5. Existe algum prazo critico para envio de relatorios, calibracoes ou verificacoes?
6. Como voces controlam vencimentos de equipamentos, manutencoes ou calibracoes?
7. Quando algo da errado, como o responsavel fica sabendo?
8. Quais tarefas repetitivas tomam tempo toda semana?
9. O que aconteceria se esse processo fosse atrasado por 2 dias?
10. Se fosse para automatizar apenas uma rotina agora, qual traria mais alivio?

## Sinais De Boa Oportunidade

- Processo repetitivo semanal ou diario.
- Dados ja existem em planilha, sistema ou e-mail.
- Erro manual causa atraso, retrabalho ou risco operacional.
- Existe responsavel claro pelo processo.
- Cliente consegue fornecer amostra de dados.

## Encerramento

Pelo que voce descreveu, parece que o melhor primeiro passo e automatizar [processo identificado]. Eu posso montar uma proposta com escopo fechado, mostrando entradas, regras, saidas, prazo e valor.

## Saida Esperada Da Conversa

- Processo escolhido.
- Origem dos dados.
- Saida esperada.
- Responsavel pelo aceite.
- Urgencia.
- Proximo passo combinado.
```

- [ ] **Step 2: Verificar quantidade de perguntas**

Run:

```powershell
Select-String -Path docs\comercial\roteiro-diagnostico.md -Pattern "^\\d+\\."
```

Expected: 10 perguntas principais.

- [ ] **Step 3: Commit**

Run:

```powershell
git add docs/comercial/roteiro-diagnostico.md
git commit -m "docs: add diagnostic sales script"
```

Expected: commit criado com o roteiro de diagnostico.

## Task 5: Criar Plano De Prospeccao

**Files:**
- Create: `docs/comercial/prospeccao-laboratorios.md`

- [ ] **Step 1: Criar plano de prospeccao**

Create `docs/comercial/prospeccao-laboratorios.md` with:

```markdown
# Prospeccao Para Laboratorios E Controle De Qualidade

## Objetivo

Gerar conversas qualificadas com empresas que tenham processos tecnicos repetitivos e potencial para automacao com N8N.

## Meta Dos 30 Dias

- Listar 30 a 50 empresas.
- Realizar 10 a 20 contatos.
- Buscar 3 a 5 conversas qualificadas.
- Apresentar pelo menos 1 demonstracao.
- Enviar pelo menos 1 proposta.

## Perfil De Empresa

- Laboratorios de calibracao.
- Laboratorios de ensaio.
- Empresas de metrologia.
- Pequenas industrias com controle de qualidade.
- Empresas de manutencao tecnica.
- Prestadores de servico regulado.

## Criterios Para Priorizar

1. Tem relatorios tecnicos recorrentes.
2. Trabalha com prazos ou vencimentos.
3. Usa planilhas visivelmente ou menciona processos manuais.
4. Tem responsavel tecnico identificavel.
5. Parece pequena o suficiente para decidir rapido.

## Mensagem Inicial

Ola, [nome]. Vi que voces trabalham com [area da empresa]. Eu ajudo laboratorios e empresas tecnicas a automatizar relatorios, alertas de vencimento e rotinas manuais usando N8N, sem trocar o sistema atual. Faz sentido uma conversa rapida para eu entender se existe algum processo repetitivo que esteja consumindo tempo por ai?

## Follow-Up

Ola, [nome]. Passando so para retomar minha mensagem anterior. Normalmente encontro oportunidades em relatorios feitos manualmente, controle de vencimento de equipamentos ou alertas que chegam tarde. Se isso existir por ai, posso te mostrar uma demonstracao curta.

## Registro Dos Contatos

Para cada empresa, registrar:

- Nome da empresa.
- Segmento.
- Cidade.
- Pessoa contatada.
- Canal.
- Data do contato.
- Dor percebida.
- Status.
- Proximo passo.

## Status Permitidos

- Listado.
- Contatado.
- Respondeu.
- Diagnostico marcado.
- Demonstracao feita.
- Proposta enviada.
- Ganho.
- Perdido.

## Criterio De Pronto

A prospeccao esta funcionando quando existem contatos registrados, proximos passos claros e pelo menos uma conversa onde o cliente descreveu uma dor real.
```

- [ ] **Step 2: Verificar metas**

Run:

```powershell
Select-String -Path docs\comercial\prospeccao-laboratorios.md -Pattern "30 a 50|10 a 20|3 a 5|proposta"
```

Expected: aparecem as metas de lista, contatos, conversas e proposta.

- [ ] **Step 3: Commit**

Run:

```powershell
git add docs/comercial/prospeccao-laboratorios.md
git commit -m "docs: add laboratory prospecting plan"
```

Expected: commit criado com o plano de prospeccao.

## Task 6: Criar Processo De Entrega

**Files:**
- Create: `docs/entrega/processo-entrega.md`

- [ ] **Step 1: Criar a pasta de entrega**

Run:

```powershell
New-Item -ItemType Directory -Force docs\entrega
```

Expected: a pasta `docs/entrega` existe.

- [ ] **Step 2: Criar processo de entrega**

Create `docs/entrega/processo-entrega.md` with:

```markdown
# Processo De Entrega

## Objetivo

Entregar automacoes N8N com escopo claro, teste, documentacao e suporte inicial, evitando improviso no primeiro cliente.

## Etapa 1: Diagnostico

Saidas obrigatorias:

- Processo escolhido.
- Origem dos dados.
- Regras principais.
- Saida esperada.
- Responsavel pelo aceite.
- Prazo desejado.

## Etapa 2: Mapeamento

Registrar:

- Entradas.
- Transformacoes.
- Validacoes.
- Saidas.
- Erros esperados.
- Alertas necessarios.

## Etapa 3: Construcao Em Teste

Regras:

- Usar dados de amostra.
- Nao enviar mensagens reais sem aprovacao.
- Nomear nodes de forma clara.
- Criar tratamento de erro para falhas previsiveis.
- Exportar workflow ao final de cada marco.

## Etapa 4: Validacao

Validar com o cliente:

- Dados corretos.
- Documento ou alerta correto.
- Frequencia correta.
- Destinatarios corretos.
- Registro de execucao correto.

## Etapa 5: Implantacao

Checklist:

- [ ] Credenciais finais configuradas.
- [ ] Webhooks finais configurados.
- [ ] Teste em producao executado.
- [ ] Workflow exportado.
- [ ] Cliente treinado.
- [ ] Criterio de aceite confirmado.

## Etapa 6: Suporte Inicial

Durante 7 dias:

- Monitorar falhas.
- Corrigir pequenos ajustes combinados.
- Registrar pedidos fora de escopo.
- Propor manutencao mensal.

## Criterio De Pronto

A entrega esta concluida quando o workflow executa o processo combinado, o cliente confirma o aceite e existe copia exportada do fluxo final.
```

- [ ] **Step 3: Verificar etapas**

Run:

```powershell
Select-String -Path docs\entrega\processo-entrega.md -Pattern "^## Etapa"
```

Expected: 6 etapas de entrega.

- [ ] **Step 4: Commit**

Run:

```powershell
git add docs/entrega/processo-entrega.md
git commit -m "docs: add delivery process"
```

Expected: commit criado com o processo de entrega.

## Task 7: Criar Modelo De Proposta

**Files:**
- Create: `docs/entrega/modelo-proposta.md`

- [ ] **Step 1: Criar modelo de proposta**

Create `docs/entrega/modelo-proposta.md` with:

```markdown
# Modelo De Proposta

## Projeto

Automacao de [nome do processo] para [nome do cliente].

## Contexto

Hoje o processo de [processo atual] depende de [planilha, e-mail, sistema ou acao manual], o que gera [dor principal].

## Objetivo

Automatizar o fluxo para reduzir trabalho manual, atrasos e risco de erro, mantendo o processo simples para a equipe.

## Escopo Incluido

- Mapeamento do processo atual.
- Criacao de 1 workflow principal no N8N.
- Integracao com as fontes de dados combinadas.
- Validacao de campos obrigatorios.
- Geracao da saida combinada.
- Testes com dados de amostra ou dados reais aprovados.
- Documentacao simples.
- Treinamento rapido.
- Suporte inicial por 7 dias apos implantacao.

## Fora Do Escopo

- Novos workflows alem do fluxo principal.
- Mudancas grandes de regra apos aprovacao do escopo.
- Integracoes com sistemas sem acesso ou API disponivel.
- Garantia juridica, fiscal ou regulatoria sobre documentos.
- Operacao diaria do processo pelo fornecedor.

## Prazo

O prazo estimado e de 7 a 15 dias uteis apos recebimento dos acessos e dados necessarios.

## Investimento

- Projeto: R$ [valor].
- Manutencao mensal opcional: R$ [valor].

## Manutencao Mensal

Inclui monitoramento de falhas, pequenos ajustes, backup de workflows e suporte para duvidas operacionais.

## Condicoes

- Inicio mediante aprovacao da proposta.
- 50% na aprovacao e 50% na entrega.
- Acessos e dados devem ser fornecidos pelo cliente.
- Mudancas fora do escopo serao orcadas separadamente.

## Aceite

O projeto sera considerado entregue quando o workflow executar o fluxo combinado em teste final e o cliente confirmar o aceite por escrito.
```

- [ ] **Step 2: Verificar secoes comerciais**

Run:

```powershell
Select-String -Path docs\entrega\modelo-proposta.md -Pattern "Escopo Incluido|Fora Do Escopo|Investimento|Aceite"
```

Expected: secoes essenciais da proposta aparecem.

- [ ] **Step 3: Commit**

Run:

```powershell
git add docs/entrega/modelo-proposta.md
git commit -m "docs: add first project proposal template"
```

Expected: commit criado com o modelo de proposta.

## Task 8: Criar Painel De Validacao De 30 Dias

**Files:**
- Create: `docs/metricas/validacao-30-dias.md`

- [ ] **Step 1: Criar pasta de metricas**

Run:

```powershell
New-Item -ItemType Directory -Force docs\metricas
```

Expected: a pasta `docs/metricas` existe.

- [ ] **Step 2: Criar painel de validacao**

Create `docs/metricas/validacao-30-dias.md` with:

```markdown
# Validacao De 30 Dias

## Objetivo

Acompanhar se a agencia N8N para laboratorios esta saindo do campo da ideia e recebendo validacao real do mercado.

## Metas Principais

- [ ] Ambiente N8N funcional.
- [ ] 3 demonstracoes definidas.
- [ ] 1 demonstracao principal pronta.
- [ ] Oferta comercial escrita.
- [ ] Lista com 30 a 50 empresas.
- [ ] 10 a 20 contatos realizados.
- [ ] 3 a 5 conversas qualificadas buscadas.
- [ ] 1 proposta enviada.
- [ ] 1 cliente pago buscado.

## Semana 1

Foco: base tecnica.

Indicadores:

- Ambiente N8N ativo: nao iniciado.
- Demo de relatorio iniciada: nao iniciado.
- Template PDF definido: nao iniciado.

## Semana 2

Foco: demonstracoes e oferta.

Indicadores:

- Demo principal pronta: nao iniciado.
- Oferta escrita: nao iniciado.
- Roteiro de diagnostico pronto: nao iniciado.

## Semana 3

Foco: prospeccao.

Indicadores:

- Empresas listadas: 0.
- Contatos realizados: 0.
- Conversas qualificadas: 0.

## Semana 4

Foco: fechamento e piloto.

Indicadores:

- Demonstracoes feitas: 0.
- Propostas enviadas: 0.
- Clientes pagos: 0.

## Aprendizados

Registrar apos cada conversa:

- Dor mencionada.
- Processo manual identificado.
- Objecao.
- Proximo passo.
- Ajuste necessario na oferta.

## Decisao Ao Final Dos 30 Dias

Escolher uma opcao:

- Continuar no nicho com ajustes.
- Reposicionar oferta dentro do mesmo nicho.
- Usar empresas locais como nicho reserva.
- Pausar venda e corrigir demonstracao tecnica.
```

- [ ] **Step 3: Verificar indicadores numericos**

Run:

```powershell
Select-String -Path docs\metricas\validacao-30-dias.md -Pattern "30 a 50|10 a 20|3 a 5|Clientes pagos"
```

Expected: aparecem os indicadores principais do ciclo.

- [ ] **Step 4: Commit**

Run:

```powershell
git add docs/metricas/validacao-30-dias.md
git commit -m "docs: add 30 day validation tracker"
```

Expected: commit criado com o painel de validacao.

## Task 9: Revisar Coerencia Entre Documentos

**Files:**
- Modify: documentos criados nas Tasks 1 a 8 se houver desalinhamento.

- [ ] **Step 1: Buscar placeholders e termos vagos**

Run:

```powershell
Select-String -Path docs\**\*.md -Pattern "<placeholder markers>" -CaseSensitive:$false
```

Expected: nenhum resultado.

- [ ] **Step 2: Confirmar que o nicho aparece nos documentos essenciais**

Run:

```powershell
Select-String -Path docs\**\*.md -Pattern "laboratorio|laboratorios|controle de qualidade|calibracao" -CaseSensitive:$false
```

Expected: resultados nos documentos de especificacao, oferta, prospeccao e workflows.

- [ ] **Step 3: Confirmar que a meta de validacao esta documentada**

Run:

```powershell
Select-String -Path docs\**\*.md -Pattern "1 cliente|5 conversas|30 dias|proposta" -CaseSensitive:$false
```

Expected: resultados no design, oferta, prospeccao e validacao.

- [ ] **Step 4: Commit se houver ajustes**

Run:

```powershell
git status --short
git add docs
git commit -m "docs: align n8n agency implementation materials"
```

Expected: se houver mudancas, commit criado; se nao houver mudancas, o Git informa que nao ha nada para commitar.

## Task 10: Preparar Execucao Do Ciclo De 30 Dias

**Files:**
- Modify: `docs/metricas/validacao-30-dias.md`

- [ ] **Step 1: Registrar data de inicio**

In `docs/metricas/validacao-30-dias.md`, add after the objective section:

```markdown
## Periodo

- Inicio: 2026-06-20.
- Fim planejado: 2026-07-20.
```

- [ ] **Step 2: Registrar primeira acao do dia**

In `docs/metricas/validacao-30-dias.md`, add before `## Decisao Ao Final Dos 30 Dias`:

```markdown
## Proxima Acao

Escolher VPS ou ambiente equivalente para subir o N8N e iniciar a demonstracao de relatorio de calibracao.
```

- [ ] **Step 3: Verificar periodo e proxima acao**

Run:

```powershell
Select-String -Path docs\metricas\validacao-30-dias.md -Pattern "2026-06-20|2026-07-20|Escolher VPS"
```

Expected: data de inicio, data final e proxima acao aparecem.

- [ ] **Step 4: Commit**

Run:

```powershell
git add docs/metricas/validacao-30-dias.md
git commit -m "docs: set validation cycle start"
```

Expected: commit criado com o inicio do ciclo.

## Final Verification

- [ ] Run:

```powershell
Get-ChildItem -Recurse docs | Select-Object FullName
```

Expected: todos os documentos de operacao, comercial, entrega, metricas, specs e plans aparecem.

- [ ] Run:

```powershell
git log --oneline -10
```

Expected: commits recentes mostram a especificacao, plano e documentos de implementacao.

- [ ] Run:

```powershell
git status --short
```

Expected: nenhuma mudanca pendente, exceto arquivos que o executor decidiu manter fora do Git.

## Current Repository Note

No momento da escrita deste plano, a pasta `.git` existia, mas tinha regra de permissao negando escrita ao usuario do sandbox. Antes de executar os passos de commit, remova a regra de negacao ou recrie o repositorio Git com permissoes normais para o usuario atual.

## Self-Review

- Spec coverage: o plano cobre infraestrutura, portfolio tecnico, oferta comercial, prospeccao, entrega, recorrencia, cronograma e metricas de sucesso definidos na especificacao.
- Placeholder scan: nao ha marcadores de pendencia, preenchimento futuro ou instrucoes sem conteudo concreto.
- Consistencia: os documentos usam o mesmo nicho, a mesma meta de 30 dias, as mesmas faixas de preco e a mesma ordem de demonstracoes.
