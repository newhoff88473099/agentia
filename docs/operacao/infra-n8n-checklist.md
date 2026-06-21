# Checklist De Infraestrutura N8N

## Objetivo

Ter um ambiente N8N simples, barato e confiavel o suficiente para demonstracoes comerciais de automacao para laboratorios e controle de qualidade, pilotos e primeiros clientes.

## Decisoes Iniciais

- Hospedagem: VPS Linux.
- Execucao: Docker.
- Banco de dados: Postgres.
- Fuso horario: America/Sao_Paulo.
- Uso inicial: demonstracao, piloto e primeiro cliente.

## Checklist Tecnico

- [ ] Contratar VPS com pelo menos 1 vCPU, 1 GB RAM e 20 GB de disco para demonstracoes; usar 2 GB RAM para pilotos e primeiros clientes com Postgres.
- [ ] Apontar dominio ou subdominio para a VPS.
- [ ] Configurar HTTPS.
- [ ] Instalar Docker e Docker Compose.
- [ ] Subir N8N com volume persistente.
- [ ] Configurar Postgres como banco de dados.
- [ ] Configurar `WEBHOOK_URL` com URL publica em HTTPS.
- [ ] Configurar `GENERIC_TIMEZONE=America/Sao_Paulo`.
- [ ] Criar usuario administrador.
- [ ] Configurar firewall, restringir SSH, expor apenas HTTP/HTTPS/SSH e revisar portas padrao abertas.
- [ ] Registrar credenciais em cofre seguro.

## Backup

- [ ] Exportar workflows apos cada mudanca relevante.
- [ ] Definir frequencia de backup do Postgres e dos workflows.
- [ ] Fazer backup do banco Postgres.
- [ ] Armazenar backups fora da VPS.
- [ ] Definir periodo de retencao dos backups.
- [ ] Guardar copia dos templates usados nas demonstracoes.
- [ ] Testar restauracao do Postgres e de pelo menos um workflow exportado.

## Logs E Alertas

- [ ] Ativar historico de execucoes no N8N.
- [ ] Configurar limpeza ou retencao dos dados de execucao para evitar crescimento de disco em VPS pequena.
- [ ] Criar workflow simples para notificar falhas criticas por e-mail.
- [ ] Registrar data, nome do workflow, erro e acao tomada.

## Criterio De Pronto

O ambiente esta pronto quando o N8N abre por HTTPS, executa um workflow de teste, persiste dados apos reinicio e permite exportar/importar workflows.

Para demonstracoes de laboratorio e controle de qualidade, validar tambem que um webhook recebe dados de amostra, o workflow grava ou atualiza um registro, um alerta de falha e disparado e o fluxo exportado/importado funciona.
