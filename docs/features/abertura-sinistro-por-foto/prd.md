# PRD — Feature: Abertura de Sinistro por Foto
**Épico:** Aviso & Abertura · **Persona:** Cliente · **Fase:** MVP
**Status:** SEMIPRONTO — complete os trechos `✍️ COMPLETAR`.

## 1. Problema / contexto
Hoje a abertura de sinistro do seguro de celular depende da central: o cliente liga, descreve o dano e envia documentos por canais dispersos. Isso gera tempo alto de abertura, sobrecarga da central e nenhuma visibilidade para o cliente. O aparelho danificado é justamente o que o cliente tem em mãos — o que torna a **captura guiada por foto no app** a alavanca natural para digitalizar essa etapa.

## 2. Objetivos e métricas de sucesso
**Objetivo:** reduzir o tempo de abertura e a carga da central, sem abrir mão de auditabilidade e controle humano sobre pagamentos.

| Métrica | O que mede | Baseline | Meta |
|---|---|---|---|
| Adoção do fluxo por foto | Aberturas via app vs. central | a medir | ≥ 40% em 90 dias |
| Tempo médio de abertura (TMA) | Início do fluxo → submissão | a medir | −50% |
| Tempo até estimativa preliminar | Submissão → estimativa exibida | novo | ≤ 5 min (p90) |
| Deflexão da central | Aberturas sem contato humano | a medir | ≥ 30% |
| CSAT do fluxo | Satisfação pós-abertura | novo | ≥ 80% de avaliações positivas (≥ 4/5) |

## 3. Escopo

**In (v1)**
- Sinistro de **dano** (físico/tela) do seguro de celular.
- App mobile (iOS/Android).
- Captura guiada de fotos com validação de qualidade.
- Estimativa preliminar automatizada.
- Triagem automática e acompanhamento de status.
- Trilha de auditoria ponta a ponta.

**Out (v1)**
- Aprovação/pagamento automático (decisão é humana).
- Sinistro de **roubo/furto** (exige boletim de ocorrência e fluxo antifraude próprio).
- **Canal web/desktop** — v1 é exclusivamente app mobile.
- **Outros ramos** de seguro (residencial, auto, etc.) — restrito ao seguro de celular.

## 4. Fluxo do usuário (em passos)
1. Cliente acessa "Abrir sinistro" (aparelho já identificado pela apólice).
2. Sistema valida elegibilidade (apólice vigente, carência, cobertura de dano).
3. Cliente informa tipo de evento, data e descrição.
4. Captura guiada de fotos: o app orienta, passo a passo, quais imagens do aparelho tirar (tela, laterais, IMEI). Cada foto passa por validação de qualidade (foco, iluminação, enquadramento); se a foto for ruim, o sistema explica o problema e pede nova captura antes de avançar.
5. Validações automáticas (qualidade das imagens + triagem por visão computacional).
6. Estimativa preliminar exibida, **com aviso explícito de que é preliminar, não uma aprovação**.
7. Cliente revisa, aceita os termos e submete; recebe número de protocolo.
8. Após a submissão, o sinistro entra em triagem automática (visão computacional + regras), que classifica e roteia o caso para a fila apropriada (análise humana quando houver indício de pagamento). O cliente acompanha o status pelo app até a decisão do analista; nenhum pagamento ocorre sem autor humano.

## 5. Riscos e considerações regulatórias
- **SUSEP** — produto regulado: a estimativa preliminar não pode ser confundida com decisão de regulação.
- **LGPD** — fotos e metadados (geolocalização/EXIF) exigem base legal, minimização e retenção definidas.
- **Não-aprovação automática** — por design, o sistema **só tria**; pagamento exige analista.
- **Fraude** — fotos de terceiros, danos pré-existentes, reuso de imagens.
- **Expectativa sobre a estimativa** — o cliente pode interpretar a faixa preliminar como valor aprovado e frustrar-se se a decisão humana divergir. Mitigação: aviso explícito de caráter preliminar, linguagem clara de que a decisão final é do analista e exibição da faixa (não de um valor único).
