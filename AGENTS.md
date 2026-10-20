# Instruções para agentes — ATLAS-ELEITORAL-DATA

Este repositório contém dados históricos e oficiais eleitorais. Antes de qualquer operação, identificar repositório, branch, SHA, worktree, origem e autorização; preservar integridade, proveniência e arquivos de dados. GitHub é a fonte versionada, nunca o Drive de intercâmbio temporário.

## Retorno obrigatório de operações executadas por IA

**Todas as IAs** que executarem escrita, testes ou procedimentos no SETUPTI e precisarem devolver resultados devem ler e cumprir integralmente o [contrato canônico de intercâmbio efêmero do JJ-DEV](https://github.com/josejunior9491/JJ-DEV/blob/main/docs/AI_EPHEMERAL_DRIVE_HANDOFF.md).

- A IA autora publica um **arquivo `.sh` versionado no GitHub**, completo e revisável, em vez de transmitir comandos longos para copiar no terminal.
- A execução gera somente um relatório sanitizado para `gdrive:JJ-DEV-INTERCAMBIO/ATLAS-ELEITORAL-DATA/`; envio deve ser confirmado por leitura reversa e SHA-256.
- **Após validação do envio, excluir somente o relatório temporário local.** Se falhar, preservá-lo e registrar falha.
- **Após leitura efetiva e registro do resultado pela IA leitora, excluir somente o relatório temporário do Drive e verificar a exclusão.** Se indisponível, declarar pendência e preservar o relatório.
- Proibido excluir dados oficiais, backups, pastas, código, documentos canônicos ou evidências permanentes. Não transmitir dados pessoais, segredos, dumps ou dados oficiais brutos como relatório. O fluxo documental não concede novas permissões nem autoriza merge/deploy.
