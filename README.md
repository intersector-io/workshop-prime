# Workshop SDD — Sinistros Digitais · Exercício de 1 hora
### Do *vibe coding* ao *Spec-Driven* · Times: PO + IT (Devs)

Ontem vocês construíram um site de abertura de sinistro **no improviso**. Hoje, em 1 hora, vocês percorrem o mesmo domínio **com método** — usando documentos já prontos como ponto de partida.

> **A ideia central:** os artefatos de produto e técnicos (Vision, Feature Map, PRD, TRD) já estão aqui. Seu trabalho não é criá-los do zero, é **completar, extrair as regras e transformar tudo em código rastreável** com o OpenSpec. É assim que um agente deixa de fazer vibe coding e passa a ser confiável.

---

## O fluxo em uma imagem

```
 vision.md → feature-map.md → [escolher 1 feature] → prd.md + trd.md
                                                          │
                                        extrair ──────────┤
                                                          ▼
                                     RF (do PRD) + RNF (do TRD)
                                                          │
                                                          ▼
                            OpenSpec:  /opsx:propose → /opsx:apply
                                       (spec acordada → código)
```

**Regra de ouro:** todo item da spec tem que apontar para um **RF** ou um **RNF**. Se não aponta, é escopo escondido.

---

## Pré-requisitos (facilitador prepara ANTES)

- Repositório clonado nas máquinas (este kit).
- OpenSpec instalado e `openspec init` já rodado no repo. Fluxo: `/opsx:propose → /opsx:apply → /opsx:archive`.
- Assistente de IA (Claude) conectado ao repo e pronto.
- Cada dupla/grupo com uma feature escolhida (ou deixe escolherem no Passo 3).

**Estrutura do kit:**
```
product/vision.md              ← pronto (revisar)
product/feature-map.md         ← pronto, ~40 features (revisar)
docs/features/<feature>/prd.md ← SEMIPRONTO (completar)
docs/features/<feature>/trd.md ← SEMIPRONTO (completar)
```
Features semiprontas: **abertura-sinistro-por-foto**, **acompanhamento-status**, **upload-documentos**.

---

## Passo a passo (60 min)

### Passo 0 · Abertura — ⏱ 4 min
🎯 Contextualizar. Mostre o fluxo acima e a regra de ouro. Frase de efeito: *"ontem no grito, hoje com spec — vamos sentir a diferença."*

### Passo 1 · Revisar o Product Vision — ⏱ 3 min
📂 `product/vision.md`
- Leia a visão, o problema, a North Star metric e os épicos.
- ✅ Pergunta para a turma: *qual é a métrica que diz se esse produto deu certo?*
- 💡 O Vision responde **por que existimos** — não é lista de telas.

### Passo 2 · Revisar o Feature Map — ⏱ 3 min
📂 `product/feature-map.md`
- Veja como os épicos se desdobram em features, com fase (MVP/N+1) e prioridade.
- ✅ Localize as 3 features marcadas com ⭐ (as que estão semiprontas).
- 💡 O Feature Map é onde o "grande" vira "fatiável".

### Passo 3 · Escolher 1 feature e completar PRD + TRD — ⏱ 15 min
📂 `docs/features/<feature-escolhida>/prd.md` **e** `.../trd.md`
- Cada grupo escolhe **uma** das 3 features ⭐.
- Abra o **PRD** e complete os trechos marcados `✍️ COMPLETAR`. Regra: PRD é **o quê/por quê**, nunca **o como**.
- Abra o **TRD** e complete os trechos marcados `✍️ COMPLETAR`. Regra: TRD é **o como técnico**, respondendo ao PRD.
- ✅ Divisão sugerida: PO no PRD, IT no TRD, com 2 min de conversa entre eles.
- 💡 Se travar, o `✍️ COMPLETAR` sempre diz o que se espera ali.

### Passo 4 · Extrair RF e RNF — ⏱ 8 min
📂 Adicione ao fim do próprio PRD/TRD (ou crie `business-rules.md` / `nfr.md`)
- Do **PRD**, extraia os **RF** (regras de negócio testáveis). Formato: `ID | regra | origem | critério Given/When/Then`.
- Do **TRD**, extraia os **RNF** (perf, segurança/LGPD, auditoria, disponibilidade). Todo RNF **precisa de número/critério**.
- ✅ Peça ao Claude: *"extraia os requisitos funcionais deste PRD como regras testáveis com cenários Given/When/Then"* — e revisem a saída.
- 💡 Momento "aha": o texto vira **regra com ID**. Um RF sem critério ou um RNF sem número **não está pronto**.

### Passo 5 · Ciclo OpenSpec — proposal + apply — ⏱ 15 min
📂 gera `openspec/changes/add-<feature>/`
- Rode `/opsx:propose "<feature>"` **passando o PRD, o TRD e os RF/RNF como contexto** para o assistente.
- Revise o `proposal.md` e as `specs/` geradas: para cada requisito, mostre **de qual RF/RNF ele veio** (rastreabilidade).
- Rode `/opsx:apply` para o assistente implementar contra a spec acordada.
- ✅ Cheque: os cenários da spec são os mesmos critérios de aceite dos RF? Deveriam ser.
- 💡 Aqui o PRD/TRD são **insumos de origem**, não decoração. É o que impede o agente de "inventar".

### Passo 6 · Ver executando — ⏱ 4 min
- Rode o que o `/opsx:apply` gerou (nem que seja o esqueleto/preview).
- ✅ O ponto **não** é entregar produção — é ver a **spec virar código rastreável** em minutos.
- 💡 Compare mentalmente com o site de ontem: dá para saber *por que* cada parte existe?

### Passo 7 · Feedback da turma — ⏱ 8 min
Rode as perguntas abaixo (rápidas, todos respondem):
1. Onde estava o **esforço de verdade** — pensar/decidir ou digitar?
2. O que mudou em relação a **ontem** (vibe coding)? O que melhorou, o que ficou mais lento?
3. Qual artefato foi **mais difícil** de completar e por quê?
4. Onde a **IA acelerou** e onde ela **ainda precisou de decisão humana**?
5. Daqui a 3 meses, para evoluir a feature, vocês partem **do site de ontem ou desta spec**? Por quê?

---

## Resumo dos tempos

| Passo | O quê | Tempo |
|------|-------|------|
| 0 | Abertura | 4 min |
| 1 | Revisar Vision | 3 min |
| 2 | Revisar Feature Map | 3 min |
| 3 | Completar PRD + TRD | 15 min |
| 4 | Extrair RF + RNF | 8 min |
| 5 | OpenSpec: propose + apply | 15 min |
| 6 | Ver executando | 4 min |
| 7 | Feedback | 8 min |
| | **Total** | **60 min** |

---

## Anti-padrões (o facilitador vigia)

- PRD falando de tecnologia → o "como" vazou, devolva pro TRD.
- RF vaga ("deve ser fácil de usar") → não é testável.
- RNF sem número ("tem que ser rápido") → exija a métrica (ex.: ≤ 5 min p90).
- Spec sem rastreio pra RF/RNF → é vibe coding com etapas a mais.
- TRD que esquece as restrições regulatórias do PRD (auditoria, não-aprovação automática) → o erro mais comum.
