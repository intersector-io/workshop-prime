# Feature Map — Sinistros Digitais

Legenda de fase: **MVP** = primeira entrega · **N+1** = incremento seguinte · **N+2** = futuro.
⭐ = feature **semipronta** neste kit (PRD + TRD para completar no exercício).

## Épico 1 — Aviso & Abertura
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| ⭐ Abertura de sinistro por foto | Registrar dano com fotos guiadas + estimativa preliminar | Cliente | MVP | Alta |
| Abertura assistida por chat | Assistente conversacional conduz a abertura | Cliente | N+1 | Média |
| Abertura por formulário guiado | Fluxo em formulário passo a passo | Cliente | MVP | Média |
| Seleção automática do bem segurado | App já identifica o aparelho pela apólice | Cliente | MVP | Alta |
| Validação de elegibilidade | Checa apólice, carência e cobertura | Cliente | MVP | Alta |
| Pré-aviso de sinistro | Registrar a intenção antes de ter tudo em mãos | Cliente | N+1 | Baixa |
| Abertura por roubo/furto | Fluxo com B.O. e trilha probatória | Cliente | N+1 | Média |

## Épico 2 — Triagem & Análise
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| Triagem automática e roteamento | Classifica e encaminha o caso para a fila certa | Analista | MVP | Alta |
| Estimativa preliminar automatizada | Gera faixa/valor preliminar por visão computacional | Cliente | MVP | Alta |
| Detecção de indícios de fraude | Sinaliza casos suspeitos para revisão reforçada | Analista | MVP | Alta |
| Fila de análise (backoffice) | Painel do analista com priorização | Analista | MVP | Alta |
| Solicitação de documentação adicional | Pede ao cliente o que faltou | Analista | MVP | Média |
| Classificação por classe de serviço | Prioriza por urgência/tipo | Analista | N+1 | Baixa |

## Épico 3 — Acompanhamento & Comunicação
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| ⭐ Acompanhamento de status do sinistro | Ver o andamento e próximos passos no app | Cliente | MVP | Alta |
| Notificações de mudança de status | Push/e-mail/SMS/WhatsApp a cada mudança | Cliente | MVP | Alta |
| Linha do tempo do sinistro | Histórico visual de eventos | Cliente | N+1 | Média |
| Central de mensagens | Cliente ↔ analista dentro do app | Cliente | N+1 | Média |
| SLA / prazo estimado visível | Mostra o prazo previsto de cada etapa | Cliente | N+1 | Média |
| Reabertura / contestação | Reabrir ou contestar uma decisão | Cliente | N+2 | Baixa |

## Épico 4 — Documentação & Evidências
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| ⭐ Upload de documentos complementares | Enviar documentos pedidos pela análise | Cliente | MVP | Alta |
| Captura guiada de fotos com validação | Feedback de qualidade em tempo real | Cliente | MVP | Alta |
| Assinatura eletrônica de termos | Aceite/assinatura digital | Cliente | N+1 | Média |
| Cofre de documentos do sinistro | Repositório dos anexos do caso | Cliente | N+1 | Baixa |
| OCR / extração de dados | Lê dados de nota fiscal/documentos | Sistema | N+2 | Baixa |

## Épico 5 — Resolução & Pagamento
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| Aprovação humana de pagamento (gate) | Analista decide; sistema nunca aprova sozinho | Analista | MVP | Alta |
| Escolha da forma de indenização | Reparo, troca ou PIX | Cliente | N+1 | Média |
| Acompanhamento de reparo/logística | Status da assistência técnica | Cliente | N+2 | Baixa |
| Comprovante de resolução | Documento final do sinistro | Cliente | N+1 | Média |
| CSAT pós-resolução | Pesquisa de satisfação | Cliente | MVP | Média |

## Épico 6 — Autoatendimento de Apólice
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| Segunda via de apólice | Baixar a apólice no app | Cliente | N+1 | Média |
| Consulta de coberturas e franquia | Ver o que está coberto | Cliente | MVP | Média |
| Atualização de dados cadastrais | Editar dados pessoais | Cliente | N+1 | Baixa |
| Histórico de sinistros | Lista de sinistros anteriores | Cliente | N+1 | Baixa |

## Épico 7 — Prevenção & Educação
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| Dicas de prevenção personalizadas | Reduzir sinistros com orientação | Cliente | N+2 | Baixa |
| FAQ / ajuda contextual | Central de ajuda dentro do fluxo | Cliente | MVP | Média |

## Épico 8 — Confiança, Compliance & Auditoria *(transversal)*
| Feature | Descrição curta | Persona | Fase | Prioridade |
|---|---|---|---|---|
| Trilha de auditoria ponta a ponta | Log imutável de eventos e decisões | Compliance | MVP | Alta |
| Guardrail de não-aprovação automática | Impede pagamento sem autor humano | Compliance | MVP | Alta |
| Gestão de consentimento LGPD | Base legal e retenção de dados/fotos | Compliance | MVP | Alta |
| Explicabilidade das decisões de IA | Registrar as razões da triagem/estimativa | Compliance | N+1 | Média |
