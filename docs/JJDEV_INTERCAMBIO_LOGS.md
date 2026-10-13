# Regra canônica — intercâmbio e limpeza de diagnósticos

Esta aplicação adota a política central de JJ-DEV: [docs/PADRAO_DRIVE_INTERCAMBIO_PROJETOS.md](https://github.com/josejunior9491/JJ-DEV/blob/docs/padrao-drive-intercambio-projetos-20261013/docs/PADRAO_DRIVE_INTERCAMBIO_PROJETOS.md) (PR #4, pendente de merge).

- Destino de relatórios técnicos **sanitizados**: `gdrive:JJ-DEV-INTERCAMBIO/ATLAS-ELEITORAL-DATA/`. Uma subpasta por projeto, dentro da raiz única; nunca criar raízes paralelas.
- Validar e sanitizar o relatório, enviar via rclone, confirmar sucesso e integridade remota (tamanho/checksum quando suportado) e **excluir automaticamente e imediatamente somente o arquivo temporário local enviado**. Em falha, preservar o arquivo. Logs brutos e registros sujeitos a retenção não entram nessa limpeza.
- Após leitura integral, análise concluída e registro sintético não sensível, oferecer comando de exclusão do **arquivo específico** no Drive, mediante autorização; conferir resultado.
- Inventariar relatórios antigos locais e remotos; excluir somente após classificação, confirmação de inutilidade e autorização. Não usar deleção automática por idade nem recursiva.
- Preservar logs operacionais e evidências necessárias a reprodução, auditoria, incidentes, segurança, backups, obrigações legais ou políticas corporativas. Exclusão não equivale a eliminação de backups, lixeiras ou históricos.
- Usar `umask 077`, diretórios locais ignorados pelo Git e caminho absoluto validado para a exclusão pontual automática após upload. Nunca apagar recursivamente.

**Status:** registro documental. Implementação e homologação dos comandos de limpeza são tarefas separadas; nenhum log existente foi excluído.
