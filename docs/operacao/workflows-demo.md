# Workflows Demonstraveis Para Laboratorios

## Objetivo

Criar 3 demonstracoes comerciais que mostrem valor pratico para laboratorios, controle de qualidade, calibracao e operacoes tecnicas.

## Demo 1: Relatorio De Calibracao

### Dor

Relatorios feitos manualmente em planilha ou editor de texto consomem tempo, geram erro de preenchimento e atrasam envio ao cliente.

### Escopo MVP

- Fonte de dados: Google Sheets.
- Canal de saida: PDF enviado por e-mail.
- Fora do MVP: Excel, formulario, assinatura digital, portal do cliente e integracoes com ERP.

### Fluxo

1. Receber dados por Google Sheets.
2. Validar campos obrigatorios: cliente, equipamento, numero de serie, data, responsavel e resultado.
3. Gerar PDF com template padrao.
4. Enviar PDF por e-mail ao cliente.
5. Registrar status do envio.

Excel e formulario sao adaptacoes posteriores, fora da demonstracao MVP.

### Criterios De Aceite

- [ ] Dados incompletos nao geram PDF.
- [ ] PDF contem cliente, equipamento, data e resultado.
- [ ] E-mail e enviado com assunto padronizado.
- [ ] Execucao fica registrada com timestamp, cliente, equipamento, status e mensagem de erro quando aplicavel.

### Criterio De Pronto

A demonstracao esta pronta quando gera um PDF e envia um e-mail usando dados simulados do Google Sheets, mostrando tambem um caso bloqueado por dados incompletos e o respectivo registro de execucao.

## Demo 2: Agenda E Manutencao De Equipamentos

### Dor

Vencimentos de calibracao, manutencao ou verificacao sao esquecidos quando dependem de controle manual.

### Escopo MVP

- Fonte de dados: Google Sheets com cadastro de equipamentos.
- Canal de saida: e-mail de alerta ao responsavel.
- Fora do MVP: WhatsApp, calendario corporativo, ordem de servico e integracoes com sistemas de manutencao.

### Fluxo

1. Ler planilha de equipamentos.
2. Identificar equipamentos vencidos e equipamentos com vencimento nos proximos 30 dias.
3. Agrupar a urgencia no texto do alerta em faixas: vencido, ate 7 dias, ate 15 dias ou ate 30 dias.
4. Enviar aviso por e-mail ao responsavel.
5. Marcar equipamento como notificado.

### Criterios De Aceite

- [ ] Equipamentos vencidos ou com vencimento nos proximos 30 dias sao detectados.
- [ ] Responsavel recebe alerta com nome do equipamento, numero de serie, data de vencimento, responsavel e urgencia/status.
- [ ] Equipamentos ja notificados nao geram duplicidade no mesmo ciclo.

### Criterio De Pronto

A demonstracao esta pronta quando identifica pelo menos um equipamento vencido e um equipamento a vencer, envia alerta com as faixas 7/15/30 quando aplicavel e registra quais itens foram notificados.

## Demo 3: Monitoramento De Logs Ou Processos QA

### Dor

Ocorrencias criticas ficam espalhadas em arquivos, planilhas ou sistemas e sao vistas tarde demais.

### Escopo MVP

- Fonte de dados: Google Sheets com nao conformidades.
- Canal de saida: e-mail de alerta ao responsavel.
- Fora do MVP: webhooks, arquivos de log, WhatsApp, integracao com LIMS, Jira ou sistemas de qualidade.

### Fluxo

1. Ler planilha de nao conformidades no Google Sheets.
2. Filtrar condicoes criticas: severidade Alta ou Critica, status Aberta, ou SLA excedido.
3. Enviar alerta ao responsavel.
4. Registrar historico de ocorrencias.

### Criterios De Aceite

- [ ] Eventos normais nao geram alerta.
- [ ] Eventos criticos geram alerta com origem, timestamp, severidade, descricao do evento e acao recomendada.
- [ ] Historico registra data, origem, severidade e acao tomada.

### Criterio De Pronto

A demonstracao esta pronta quando a planilha simulada de nao conformidades gera alerta apenas para regras criticas e registra o historico com contexto suficiente para decisao operacional.

## Ordem De Construcao

1. Relatorio de calibracao.
2. Agenda e manutencao.
3. Monitoramento QA.

## Criterio De Pronto

O conjunto esta pronto quando as 3 demonstracoes podem ser apresentadas em ate 10 minutos, com dados simulados realistas e explicacao direta do ganho operacional de cada fluxo.
