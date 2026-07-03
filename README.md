# Workshop SDD — Sinistros Digitais · Exercício de 1 hora
### Do *vibe coding* ao *Spec-Driven* · Times: PO + IT (Devs)

Ontem vocês construíram um site de abertura de sinistro **no improviso**. Hoje, em 1 hora, vocês percorrem o mesmo domínio **com método** — usando documentos já prontos como ponto de partida.

> **A ideia central:** os artefatos de produto (Vision, Feature Map, PRD) já estão aqui. Seu trabalho não é criá-los do zero, é **completar, extrair as regras e transformar tudo em código rastreável** com o OpenSpec. É assim que um agente deixa de fazer vibe coding e passa a ser confiável.

---

## O fluxo em uma imagem

```
 vision.md → feature-map.md → [escolher 1 feature] → prd.md
                                                        │
                                     grill-me ──────────┤  (completar gaps + melhorar)
                                                        ▼
                                    OpenSpec:  /opsx:new
                                    (spec acordada → artefatos rastreáveis)
```

**Regra de ouro:** todo item da spec tem que apontar para uma regra do **PRD**. Se não aponta, é escopo escondido.

---

## Setup — instalação das ferramentas

### 0. Instalar o Node.js (inclui `npm` e `npx`)

Os comandos abaixo (`npm` e `npx`) exigem o **Node.js** instalado. O `npm` e o `npx` já vêm juntos na instalação do Node.js.

**Windows / macOS:**
- Baixe o instalador **LTS** em [nodejs.org](https://nodejs.org/) e execute-o (Next → Next → Finish).
- Alternativa via gerenciador de pacotes:
  - Windows (winget): `winget install OpenJS.NodeJS.LTS`
  - macOS (Homebrew): `brew install node`

**Linux (Debian/Ubuntu):**
```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

**Verifique a instalação** (reabra o terminal se necessário):
```bash
node --version
npm --version
npx --version
```
Se os três comandos exibirem uma versão, o `npm` e o `npx` estão prontos para os próximos passos.

### 1. Instalar o OpenSpec

```bash
npm install -g @fission-ai/openspec@latest
cd your-project
openspec init
```

### 2. Instalar as skills do pacote `mattpocock/skills`

```bash
npx skills@latest add mattpocock/skills
```

No fluxo interativo:
- Selecione o pacote com a **barra de espaço** e pressione **Enter**.
- Selecione **Claude Code** e pressione **Enter**.
- Selecione o escopo **Global** e pressione **Enter**.
- Escolha **Symlink** e pressione **Enter**.

### 3. Verificar que está tudo pronto ✅

Antes de começar o exercício, confirme que as ferramentas e os comandos estão disponíveis:

- [ ] `node --version`, `npm --version` e `npx --version` retornam uma versão (Node.js OK).
- [ ] `openspec --version` retorna uma versão (OpenSpec instalado).
- [ ] No **Claude Code**, digite `/` e confirme que o comando **`/grill-me`** aparece na lista de skills.
- [ ] No **Claude Code**, digite `/` e confirme que o comando **`/opsx:new`** aparece na lista.

Se algum item falhar:
- `/grill-me` não aparece → refaça o **Passo 2** (skills do `mattpocock/skills`) e reinicie o Claude Code.
- `/opsx:new` não aparece → confirme que o `openspec init` foi rodado neste repo (**Passo 1**) e reinicie o Claude Code.

---

## Pré-requisitos (facilitador prepara ANTES)

- Repositório clonado nas máquinas (este kit).
- OpenSpec instalado e `openspec init` já rodado no repo (ver **Setup** acima). Fluxo: `/opsx:new`.
- Skills do pacote `mattpocock/skills` instaladas (ver **Setup** acima) — inclui a skill `grill-me`.
- Assistente de IA (Claude) conectado ao repo e pronto.
- Cada dupla/grupo com uma feature escolhida (ou deixe escolherem no Passo 3).

**Estrutura do kit:**
```
product/vision.md              ← pronto (revisar)
product/feature-map.md         ← pronto, ~40 features (revisar)
docs/features/<feature>/prd.md ← SEMIPRONTO (completar)
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

### Passo 3 · Escolher 1 feature e completar o PRD com a skill `grill-me` — ⏱ 20 min
📂 `docs/features/<feature-escolhida>/prd.md`
- Cada grupo escolhe **uma** das 3 features ⭐.
- Abra o **PRD** e localize os trechos marcados `✍️ COMPLETAR`.
- Rode a skill **`grill-me`** (do pacote `mattpocock/skills`) para **preencher os gaps `COMPLETAR` e melhorar o PRD**: ela questiona o time até as decisões ficarem explícitas e testáveis.

  Exemplo de prompt para o assistente:
  ```
  Avalie o PRD docs\features\abertura-sinistro-por-foto\prd.md e o product\vision.md e use /grill-me para responder os gaps "COMPLETAR" e melhorar o PRD
  ```
- Regra: PRD é **o quê/por quê**, nunca **o como**.
- ✅ Divisão sugerida: PO conduz as respostas de negócio, IT desafia a viabilidade, com a `grill-me` puxando os pontos ainda abertos.
- 💡 Se travar, o `✍️ COMPLETAR` sempre diz o que se espera ali — e a `grill-me` te empurra a fechar.

### Passo 4 · Ciclo OpenSpec — `/opsx:new` — ⏱ 22 min
📂 gera `openspec/changes/add-<feature>/`
- Rode `/opsx:new` **passando o PRD completado como contexto** para o assistente.
- ⚠️ O OpenSpec trabalha em **etapas**: depois do `/opsx:new`, o fluxo **não termina de uma vez**. A cada etapa ele vai pedir que você rode **`/opsx:continue`** para seguir para a próxima — repita quantas vezes for necessário.
- Só rode **`/opsx:apply`** no **final**, quando todos os artefatos já estiverem revisados e acordados. Sequência típica: `/opsx:new` → `/opsx:continue` → `/opsx:continue` → … → `/opsx:apply`.
- A cada etapa do fluxo, **confira os artefatos gerados** antes de avançar: o `proposal.md`, as `specs/` e os cenários.
- Para cada requisito da spec, mostre **de qual regra do PRD ele veio** (rastreabilidade).
- ✅ Cheque: os cenários da spec são os mesmos critérios de aceite do PRD? Deveriam ser.
- 💡 Aqui o PRD é **insumo de origem**, não decoração. É o que impede o agente de "inventar".

### Passo 5 · Feedback da turma — ⏱ 8 min
Rode as perguntas abaixo (rápidas, todos respondem):
1. Onde estava o **esforço de verdade** — pensar/decidir ou digitar?
2. O que mudou em relação a **ontem** (vibe coding)? O que melhorou, o que ficou mais lento?
3. Qual parte do PRD foi **mais difícil** de completar e por quê?
4. Onde a **IA acelerou** e onde ela **ainda precisou de decisão humana**?
5. Daqui a 3 meses, para evoluir a feature, vocês partem **do site de ontem ou desta spec**? Por quê?

---

## Resumo dos tempos

| Passo | O quê | Tempo |
|------|-------|------|
| 0 | Abertura | 4 min |
| 1 | Revisar Vision | 3 min |
| 2 | Revisar Feature Map | 3 min |
| 3 | Completar PRD com `grill-me` | 20 min |
| 4 | OpenSpec: `/opsx:new` | 22 min |
| 5 | Feedback | 8 min |
| | **Total** | **60 min** |

---

## Anti-padrões (o facilitador vigia)

- PRD falando de tecnologia → o "como" vazou, é só o quê/por quê.
- Regra vaga ("deve ser fácil de usar") → não é testável; use a `grill-me` para forçar o critério.
- Requisito sem número ("tem que ser rápido") → exija a métrica (ex.: ≤ 5 min p90).
- Spec sem rastreio pra regra do PRD → é vibe coding com etapas a mais.
- PRD que esquece as restrições regulatórias (auditoria, não-aprovação automática) → o erro mais comum.
