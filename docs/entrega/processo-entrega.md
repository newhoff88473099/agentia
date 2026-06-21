# Processo De Entrega

## Objetivo

Entregar automacoes N8N com escopo claro, teste, documentacao e suporte inicial, evitando improviso no primeiro cliente.

Este processo deve ser usado depois do diagnostico e da proposta aprovados, mantendo evidencias simples de aceite, exportacao e mudancas fora de escopo.

## Etapa 1: Diagnostico

Saidas obrigatorias:

- Processo escolhido.
- Origem dos dados.
- Regras principais.
- Saida esperada.
- Criterios de aceite.
- Dependencias e forma de acesso.
- Referencia da proposta ou escopo aprovado.
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
- Dependencias externas.
- Acessos necessarios, sem registrar senhas.
- Criterios de aceite por saida.

## Etapa 3: Construcao Em Teste

Regras:

- Usar dados de amostra.
- Nao enviar mensagens reais sem aprovacao.
- Nomear nodes de forma clara.
- Criar tratamento de erro para falhas previsiveis.
- Exportar workflow ao final de cada marco.

Marco significa uma versao relevante do fluxo: apos construcao em teste, apos validacao do cliente, antes da producao e apos aceite em producao.

## Etapa 4: Validacao

Validar com o cliente:

- Dados corretos.
- Documento ou alerta correto.
- Frequencia correta.
- Destinatarios corretos.
- Registro de execucao correto.
- Evidencia de aceite registrada por mensagem, email ou documento.
- Escopo validado contra a proposta aprovada.

## Etapa 5: Implantacao

Checklist:

- [ ] Credenciais finais configuradas.
- [ ] Webhooks finais configurados.
- [ ] Primeiro teste em producao executado com gatilho controlado, amostra pequena e destinatarios aprovados.
- [ ] Workflow exportado.
- [ ] Copia de rollback ou versao anterior preservada quando existir.
- [ ] Documentacao simples entregue com objetivo do workflow, entradas, saidas, credenciais usadas sem senhas, pontos de monitoramento e contato de suporte.
- [ ] Cliente treinado.
- [ ] Criterio de aceite confirmado.

Se a implantacao falhar, desabilitar o novo workflow, restaurar a versao anterior ou exportada, registrar a causa e confirmar com o responsavel pelo aceite se o rollback deve permanecer ativo.

## Etapa 6: Suporte Inicial

Durante 7 dias:

- Monitorar falhas.
- Corrigir pequenos ajustes combinados.
- Registrar pedidos fora de escopo.
- Propor manutencao mensal.

Pequenos ajustes nao incluem novas integracoes, novos fluxos ou mudancas grandes de regra.

Pedidos fora de escopo devem voltar para a oferta ou proposta aprovada e virar nova proposta, ajuste formal ou item para manutencao recorrente.

## Criterio De Pronto

A entrega esta concluida quando o workflow executa o processo combinado, o cliente confirma o aceite e existe copia exportada do fluxo final.
