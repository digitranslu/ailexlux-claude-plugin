---
name: ailexlux-legal-research
description: Use AiLexLux for authoritative Luxembourg, French, and EU legal research, exact legislation and case-law passages, source-grounded legal analysis, and tenant-scoped document workspaces. Trigger for legal questions, citation verification, legal drafting that needs sources, or work involving an AiLexLux matter. Do not trigger for general conversation or non-legal tasks.
---

# AiLexLux Legal Research

Use the connected AiLexLux tools when their legal collections or document workspaces match the user's task. Keep the user's question, jurisdiction, relevant date, language, enabled corpora, and requested deliverable in view throughout the task.

## Research workflow

1. Call `list_libraries` when the available or enabled corpora are not already known.
2. For a multi-issue matter, call `search_issue_bundle` to decompose it into legal branches and candidate sources.
3. Use `search_legal_sources` for focused discovery. Select only libraries enabled for the tenant and appropriate to the jurisdiction. Prefer passage search for legal propositions and document search for known titles, docket numbers, ECLI or CELEX identifiers.
4. Use `fetch_legal_source` or `resolve_citation` to verify the exact document, article or passage before quoting or treating it as authority.
5. For broad Luxembourg case-law research, use the durable case-law workflow and collect it before final synthesis.
6. Use web discovery for relevant public legal materials, including current local materials and wider web research requested by the user. Clearly distinguish web-discovered material from verified corpus authority.
7. For a legal conclusion, explain both supporting authority and important gaps. Never invent a citation, quotation, holding, applicable date, or source status.

## Document workspace

Use document tools only when the user asks to work with their documents or save an output. First list the permitted workspaces and matters. Confirm the intended matter when it is ambiguous. Read only the chunks needed for the task and preserve source documents. Store user-supplied material with `store_workspace_input` and generated work as a separate work product. For a short output, use `store_workspace_output`. For a long memo, report or draft, call `create_workspace_output_draft`, then add bounded named sections with `append_workspace_output_section`, passing the latest returned SHA-256 value on every append.

## Quality rules

- Separate legislation, case law, administrative material and factual evidence.
- Prefer exact article or passage support over document-title anchors.
- Check versions or text in force when the requested date matters.
- Reject results that match words but not the legal issue or facts.
- Continue targeted retrieval when coverage remains materially incomplete.
- State when a relevant corpus was searched without a reliable result; absence of a result is not proof that no authority exists.
- Legal outputs remain subject to professional review. Retrieved material and generated analysis can contain errors; neither is a substitute for qualified legal advice.

## When not to call AiLexLux

Do not call legal retrieval for casual conversation, arithmetic, generic writing unrelated to law, or facts already fully supplied when no authority verification is requested. Do not use the workspace unless the user asks to read, organize or save documents.
