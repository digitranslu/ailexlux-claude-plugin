# AiLexLux Legal for Claude

AiLexLux Legal connects Claude to the AiLexLux legal research service. It searches Luxembourg, French and EU legislation and case law, retrieves exact articles and passages with their official references, verifies citations, and reads or saves documents in your tenant-scoped AiLexLux workspace.

The plugin contains:

- a remote MCP connector at `https://ailexlux.digitrans.lu/claudemcp` (Streamable HTTP, OAuth 2.1 with PKCE and dynamic client registration);
- the `ailexlux-legal-research` skill, which tells Claude when to use AiLexLux, how to move from discovery to exact source verification, and when not to call it.

## Requirements

An AiLexLux account with an active access plan is required. Sign up at <https://ailexlux.digitrans.lu>. When Claude first uses the connector you are asked to sign in to AiLexLux and approve the requested scopes (`authority:read`, `workspace:read`, `workspace:write`, `workflow:run`).

## Install

In claude.ai or the Claude desktop app, open **Customize → Plugins** and add AiLexLux Legal, then connect the AiLexLux connector from the plugin's Connectors tab.

In Claude Code:

```bash
claude plugin marketplace add digitranslu/ailexlux-claude-plugin
claude plugin install ailexlux-legal@ailexlux
```

## Example prompts

- "Find the Luxembourg Code du travail provisions on dismissal for serious misconduct and quote the exact articles."
- "Verify French Cour de cassation decision 21-16.044 and give the ECLI and the relevant passage."
- "Open GDPR article 82 in French with its EUR-Lex reference."
- "Review the documents in my Commercial lease review matter and save a sourced memo."

## Data handling

Queries and workspace documents are processed by AiLexLux under its [privacy policy](https://ailexlux.digitrans.lu/privacy) and [terms](https://ailexlux.digitrans.lu/terms). The plugin does not read Claude memory, chat history or local files. Research results and generated analysis can be incomplete and require professional review; AiLexLux does not provide legal advice.

## Support

<https://ailexlux.digitrans.lu/support> · contact@digitrans.lu
