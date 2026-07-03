# PRD — Feature: Acompanhamento de Status do Sinistro
**Épico:** Acompanhamento & Comunicação · **Persona:** Cliente · **Fase:** MVP
**Status:** SEMIPRONTO — complete os trechos `✍️ COMPLETAR`.

## 1. Problema / contexto
Depois de abrir o sinistro, o cliente fica **no escuro**: não sabe em que etapa está, o que falta nem o prazo. Isso gera ansiedade e **ligações para a central só para perguntar "e aí?"** — o tipo de contato mais fácil de eliminar com transparência.

## 2. Objetivos e métricas de sucesso
**Objetivo:** dar visibilidade do andamento e reduzir contatos de "status" na central.

| Métrica | O que mede | Baseline | Meta |
|---|---|---|---|
| Contatos de "status" na central | Ligações só para saber andamento | a medir | −60% |
| Abertura de notificações | % de notificações lidas | novo | ≥ 50% |
| Uso da tela de status | Clientes que consultam o status no app | novo | `✍️ COMPLETAR` |
| CSAT de comunicação | Satisfação com a transparência | novo | `✍️ COMPLETAR` |

## 3. Escopo

**In (v1)**
- Tela de status do sinistro com etapa atual e próximos passos.
- Estados do sinistro: `recebido → em análise → pendente de documentação → concluído` (aprovado/negado).
- Notificação a cada mudança de status.
- Destaque claro quando **há ação pendente do cliente**.

**Out (v1)**
- Chat com atendente (fica em "Central de mensagens", N+1).
- Linha do tempo visual detalhada (N+1).
- `✍️ COMPLETAR (liste 1 item fora de escopo — dica: SLA/prazo estimado por etapa)`

## 4. Fluxo do usuário (em passos)
1. Cliente abre o detalhe de um sinistro existente.
2. Vê o **status atual** e os **próximos passos**.
3. Se há pendência (ex.: enviar documento), vê o **destaque + o que fazer**.
4. `✍️ COMPLETAR (descreva o que acontece quando o status muda enquanto o cliente NÃO está no app — pense em notificação e no que fica visível depois)`
5. Ao concluir, vê o **resultado** (aprovado/negado) e o próximo passo (ex.: comprovante).

## 5. Riscos e considerações regulatórias
- **Clareza (CDC)** — o status e os prazos precisam ser verdadeiros e compreensíveis; nada de "em análise" eterno sem explicação.
- **Notificações desativadas no SO** — status precisa continuar visível no app mesmo sem push.
- **Privacidade** — notificações não devem expor dados sensíveis na tela de bloqueio.
- `✍️ COMPLETAR (adicione 1 risco de experiência — dica: o que acontece com vários sinistros simultâneos?)`
