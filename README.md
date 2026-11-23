# MCP BISkill

Skill para o Claude consultar os BIs (Power BI) da InvestSmart/BeSmart pelo conector **Fabric IQ** seguindo 4 regras:

1. Se o dado não estiver no BI pedido, procura em outro BI e avisa qual usou.
2. SmartBonus: usa só o **BI SmartBonus 2.0**, nunca o antigo.
3. Somente leitura: não edita nada.
4. Avisa quando o dado estiver defasado.

> Pré-requisito: conector **Fabric IQ** ligado no Claude (URL `https://fabriciq.svc.cloud.microsoft/v1/mcp/fabriciq`).

## Instalar

### Claude Code
```bash
claude plugin marketplace add SEU_USUARIO/mcp-biskill
claude plugin install mcp-biskill@mcp-biskill
```

### claude.ai / Claude Desktop
1. Baixe o ZIP da pasta `skills/mcp-biskill` (ou o `mcp-biskill.zip` da release).
2. **Configurações → Capacidades → Skills → Enviar skill** e selecione o ZIP.
3. Ative a skill.

## Testar
```text
Qual o atingimento acumulado da Diretoria Comercial no SmartBonus?
```
A resposta deve usar o **BI SmartBonus 2.0**, mostrar o DAX e terminar com a data de atualização.

## Atualizar as regras
Edite `skills/mcp-biskill/SKILL.md`, faça commit e:
- Claude Code: `claude plugin marketplace update mcp-biskill`
- claude.ai: envie o ZIP de novo.

> Repositório recomendado: **privado** (contém nomes e IDs internos dos BIs).
