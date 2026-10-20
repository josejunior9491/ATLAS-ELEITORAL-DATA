# Claude Desktop no SETUPTI — orientação para ATLAS-ELEITORAL-DATA

**Estado em 20/10/2026:** o Claude Desktop do host SETUPTI possui dois conectores MCP do JJ-DEV homologados para os cenários testados. **Esta documentação não configura conector próprio de ATLAS-ELEITORAL-DATA, nem autoriza acesso aos seus dados ou arquivos.**

## Recursos transversais disponíveis no host

- `jjdev-inventory-pilot`: disponibiliza somente `list_projects`. Na homologação, o inventário retornou sete projetos; isso não equivale a permissões de leitura desses repositórios.
- `jjdev-controlled-read`: disponibiliza somente `read_approved_file`, requer `project="jj-dev"` e um `path` previamente autorizado, e lê **exclusivamente oito documentos do JJ-DEV** publicados em diretório privado no SETUPTI. Não aceita `project="atlas-eleitoral-data"`.
- Inicialização via Claude Desktop; para o leitor, o único inicializador permitido é `~/PROJETOS/JJ-DEV/experiments/mcp/launch_sandbox_reader.py`, com isolamento Bubblewrap, política de caminhos, limite de tamanho e validações de integridade.
- O teste funcional realizado no aplicativo confirmou inventário e leitura autorizada de `README.md` do JJ-DEV. Isso **não prova acesso MCP a ATLAS-ELEITORAL-DATA**.

## Como usar durante uma tarefa deste projeto

1. Identificar explicitamente `ATLAS-ELEITORAL-DATA`, repositório canônico, branch, SHA, estado das alterações e a missão. Consultar primeiro o `AGENTS.md` e a documentação de governança local quando existentes.
2. Confirmar que os conectores do JJ-DEV estão disponíveis no Claude Desktop. Se o aplicativo estava aberto durante alteração do JSON, encerrá-lo completamente e reabri-lo; não reinstalar automaticamente.
3. Usar `list_projects` apenas para descoberta. Usar `read_approved_file` **somente** para consultar documentação compartilhada e permitida do JJ-DEV, nunca como substituto de leitura do código de ATLAS-ELEITORAL-DATA.
4. Para analisar arquivos deste repositório, utilizar **meio específico efetivamente disponível e autorizado** (ex.: repositório GitHub conectado, checkout do projeto devidamente identificado ou material fornecido para a sessão). Sem esse meio, informar `ACESSO NÃO VERIFICADO` e pedir a autorização/configuração necessária; não inventar conteúdo.
5. Respeitar as políticas de dados, permissões, aprovações, PR, testes e implantação próprias do projeto. Conector MCP de inventário/leitura não concede WRITE, shell, banco, Drive, deploy, merge, faturamento nem acesso a dados sensíveis.
6. Não copiar o arquivo `claude_desktop_config.json`, credenciais, logs com dados privados ou documentos publicados para o repositório. Não ampliar a allowlist dos oito documentos ou replicar configuração em outros hosts sem aprovação separada.
7. Registrar evidências de trabalho no próprio repositório; a memória do chat e a disponibilidade do cliente Claude não substituem documentação canônica.

## Referência e limites

Fonte transversal: [JJ-DEV — Claude Desktop no SETUPTI](https://github.com/josejunior9491/JJ-DEV/blob/main/docs/CLAUDE_DESKTOP_SETUPTI.md) (**link para a documentação proposta; válido na `main` somente depois de PR aprovada/mesclada**). Consulte também `JJ-DEV/docs/AI_CONTRACT.md` e `JJ-DEV/docs/AI_TOOL_PLAYBOOK.md` na versão efetivamente acessível e aprovada.

**Não verificado neste projeto:** conector MCP específico, leitura automática do repositório por Claude, autorização para escrita e qualquer mudança operacional. A homologação existente refere-se somente aos dois servidores JJ-DEV no SETUPTI.
