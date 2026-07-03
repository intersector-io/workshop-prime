# PRD — Feature: Upload de Documentos Complementares
**Épico:** Documentação & Evidências · **Persona:** Cliente · **Fase:** MVP
**Status:** SEMIPRONTO — complete os trechos `✍️ COMPLETAR`.

## 1. Problema / contexto
Durante a análise, é comum a seguradora precisar de **documentos adicionais** (nota fiscal, B.O., laudo). Hoje esse vai-e-vem acontece por e-mail/WhatsApp, é **desorganizado, inseguro e lento**, e o cliente nunca sabe se o que enviou "chegou" ou "serve". Um canal de upload guiado dentro do sinistro fecha esse buraco.

## 2. Objetivos e métricas de sucesso
**Objetivo:** organizar e acelerar o envio de documentos pedidos pela análise, reduzindo retrabalho.

| Métrica | O que mede | Baseline | Meta |
|---|---|---|---|
| Tempo até documentação completa | Pedido → todos os docs recebidos | a medir | −40% |
| Taxa de reenvio | Documentos rejeitados que precisam reenvio | a medir | ≤ 15% |
| Docs enviados pelo app | % via app vs. e-mail/WhatsApp | novo | `✍️ COMPLETAR` |
| CSAT do envio | Satisfação com o processo de envio | novo | `✍️ COMPLETAR` |

## 3. Escopo

**In (v1)**
- Lista dos **documentos solicitados** pela análise, com status de cada um (pendente/recebido/rejeitado).
- Upload de arquivos (PDF/imagem) e captura por câmera.
- Validação básica (tipo de arquivo, tamanho, legibilidade mínima).
- Confirmação de recebimento e motivo em caso de rejeição.

**Out (v1)**
- OCR / extração automática de dados (N+2).
- Assinatura eletrônica de termos (feature própria, N+1).
- `✍️ COMPLETAR (liste 1 item fora de escopo — dica: cofre/histórico de documentos entre sinistros)`

## 4. Fluxo do usuário (em passos)
1. Cliente recebe aviso de que **faltam documentos** e abre a lista no sinistro.
2. Vê **quais documentos** são pedidos e por quê.
3. Seleciona um documento e faz upload (arquivo ou foto).
4. `✍️ COMPLETAR (descreva o que acontece quando o documento é inválido — ex.: formato errado, ilegível — e o que o cliente vê)`
5. Ao enviar tudo, o cliente vê **confirmação** e o sinistro segue para análise.

## 5. Riscos e considerações regulatórias
- **LGPD** — documentos contêm dados pessoais/sensíveis; exigem base legal, criptografia e retenção definida.
- **Segurança** — risco de upload malicioso (arquivo executável disfarçado, arquivo enorme).
- **Clareza (CDC)** — o cliente precisa saber exatamente o que é pedido e por quê.
- `✍️ COMPLETAR (adicione 1 risco — dica: documento de terceiro / fraude documental)`
