---
name: eli5
description: Use for ELI5 requests, easy explanations, or plain-language rewrites. Explain actual behavior in Korean simple enough for a five-year-old, adapting depth, difficult technical terms, and diagrams to the user's knowledge.
---

# ELI5

These instructions are written in English. Write explanations in Korean unless the user requests another language. Preserve the English-first format for difficult technical terms described below.

## When to Apply

- Apply this skill to explanations and rewrites when the user explicitly invokes `$eli5` or asks to use this skill.
- Also consider it applicable when the user requests an easy explanation without naming the skill, such as "쉽게 설명해줘" or "이해하기 쉽게 풀어 써줘". Do not apply it automatically to every explanation request.
- A request only to upload, install, or rename the skill does not require this explanation style. If the user also asks to explain or review its contents, apply the style to that explanation when appropriate.
- Do not apply the skill when the user asks not to use it. Continue to follow separate user instructions and `AGENTS.md`. Do not deliberately make an answer difficult because this skill is not in use.

## Goal

Help a first-time reader understand the main point without prior knowledge. Use words and sentence structures simple enough for a five-year-old while preserving technical meaning and avoiding baby talk.

Begin with a very short, concrete introduction in everyday Korean, simple enough for a five-year-old: answer what the subject is or what happens in one or two sentences. Put necessary conditions in the introduction when leaving them out would mislead. Explain the details below it, without expecting the reader to infer missing connections.

## Adapt to the User While Keeping the Language Simple

- Choose the depth from the user's stated knowledge and understanding demonstrated in the conversation. Do not infer complete subject knowledge from age, occupation, or use of a technical term alone.
- If the user's level is unknown, assume they are new to the subject. Start with only the essential basics instead of delaying the answer with a question about their level.
- Prefer familiar words, short sentences, and one main idea per sentence. State concretely what acts on what. Do not replace one difficult expression with another equally difficult expression.
- For a beginner, explain essential meanings and actual behavior first. When prior understanding is established, skip repetition and explain the requested principles or conditions. Keep sentences simple even when the content becomes more advanced.
- Prioritize accuracy about the requested topic. Preserve terms, conditions, exceptions, and distinctions needed for correctness, and explain their meaning. Do not list every exception unrelated to the question.
- "Simple enough for a five-year-old" is a writing criterion. Do not claim to have measured a real child's understanding or guaranteed comprehension for every reader.

## From the Overall Flow to the Details

1. Answer the main question directly in one or two very simple sentences, then give the necessary explanation below.
2. Explain the essential background and terms needed for the details.
3. Develop the details in the order introduced in the overview.
4. Explain what happens, why it happens, and how it connects to what follows, using only the detail needed.
5. Identify the actual structure, order, interactions, differences, or state changes. Show those relationships with a diagram, then explain them in clear prose. Choose steps when the reader needs to learn a sequence; otherwise use the structure that fits the question.

Do not add unnecessary outlines or steps to a simple question. Let the content determine the organization instead of forcing a fixed number of headings or list items.

Explain only the necessary basics. Do not repeat the conclusion at the end or restate already explained content in a separate section.

For questions asking how something works, how to use it, why something happens, or how concepts differ, read [references/explanation-patterns.md](references/explanation-patterns.md) and choose the relevant guidance. For a simple definition or a short rewrite, apply the main instructions directly without loading it. These patterns support judgment; they are not templates to fill out.

When explaining a process, system, comparison, or state change with diagrams, read [references/diagram-explanations.md](references/diagram-explanations.md). Use its guidance to connect the overview, each meaningful part, and prose. For a simple definition without meaningful relationships, no reference or invented diagram is needed.

## Use Diagrams for Structured Information

### When a Diagram Helps

- For each explanation request, identify aspects that benefit from structure: order, composition, containment, roles, differences, branches, interactions, cause and effect, or state changes. Show those aspects in diagrams even when the answer is short. Do not skip a meaningful diagram merely because prose can also describe it.
- Use diagrams instead of tables. For comparisons, show both subjects using the same comparison criteria and explain the practical difference in prose.
- Use Mermaid code blocks by default. If the environment is known not to support rendering, provide a readable text diagram with the same structure.
- Do not invent steps for a short definition with no meaningful structure or flow. When order or distinct parts matter, include a diagram even in a short explanation.
- Use diagrams to show actual sequences, relationships, comparisons, and state changes in the subject. Do not attach a diagram to every item in a file list, writing-rule list, or change report, or invent explanation steps merely to increase diagram count.

### Place the Overview and Step Diagrams

- For multiple steps or components, give a simple opening and a small overview diagram before the detailed explanation. Then explain the parts in the same order.
- For learning or studying a process, system, or concept in multiple substantive parts, including ordinary study requests and follow-up questions that explore a subject more deeply, include a focused diagram inside each substantive learning part, close to its prose. Do not require the user to say "detailed" or "step by step". The overview does not count as a part diagram. Group actions only when they teach the same single idea; do not invent steps or diagrams for administrative headings. Each focused diagram must show the actual action, interaction, condition, comparison, or before-and-after state, not merely repeat its title.
- Explain each step in prose: who acts, what happens, why it happens, and how it connects to the next step. Diagrams and prose must both carry useful information; a diagram alone is not an explanation. Avoid repeating each label verbatim.
- When code helps explain actual behavior, include a concise example alongside the relevant step's focused diagram and prose. Explain the important statements, their inputs and results, and show the same subjects and state changes in the diagram. State setup and example assumptions; do not imply illustrative code was executed.
- Show who acts, what they do, which subject is affected, and the result. When state changes, include the state before and after the action.
- When a part needs its own diagram, place it close to the relevant prose. Show only the current part rather than copying the entire overview repeatedly.
- Do not restate a diagram at length in prose. Let diagrams show relationships and changes while prose explains reasons and meaning, keeping the overall answer moderate in length.

### Choose the Diagram That Fits

Choose the form that best explains the current content. Do not reuse one form mechanically or duplicate the same content just to vary diagram types.

- **Processing order and branches:** Use `flowchart`. Distinguish starts, actions, conditions, and results, and label branches with their conditions.
- **Requests and responses:** Use `sequenceDiagram`. Separate actual participants, such as the user, application, and database, and show who requests what from whom and which result returns.
- **States and transition conditions:** Use `stateDiagram-v2`. Show the states before and after a change and the action or condition that causes it.
- **Components and containment:** Use `flowchart` with `subgraph`, or `mindmap`. Show what contains what and the role of each part.
- **Differences between approaches or before-and-after comparisons:** Use `flowchart` with side-by-side `subgraph` groups. Apply the same comparison criteria to each subject so the differences are clear.
- **Object responsibilities and relationships:** Use `classDiagram`. Include only relevant responsibilities and connections; do not use it when object structure is unnecessary.
- **Stored data and its relationships:** Use `erDiagram` only when explaining stored entities and their connections. Explain unfamiliar relationship notation in simple language.
- **Events and schedules over time:** Use `timeline` for event order and `gantt` for duration and overlap. Do not use schedule diagrams for ordinary processing order.

### Diagram Content and Wording

- Focus on actual subjects and actions. In technical explanations, connect user actions to internal behavior, including actual requests, methods, values, and stored results when useful.
- A flow describes processing order; a state describes a subject's current value or condition. For state changes, show the resulting state as well as the action order. When both interaction and state matter, add sequence notes or a separate small state diagram.
- Keep distinct subjects and states separate, such as an in-memory value, a database value, and a file in storage. Show unchanged states too when they help explain the next step.
- Do not present unverified values or behavior as facts. Clearly label examples and assumptions in both prose and diagrams.
- Keep each diagram focused on the current relationship. If it becomes hard to read, split it into an overview and smaller diagrams for individual steps.
- Use simple Korean and consistent names. Keep Mermaid identifiers short and stable, and make visible labels easy to understand. Do not rely on color alone; name the subjects and actions.
- Do not use metaphors, analogies, middle-dot characters, or Unicode arrow characters in the wording. Mermaid's ASCII connectors, such as `-->` and `->>`, are allowed, as are the connecting lines in rendered diagrams.

## Length

### Default Requests

- Write a moderate-length answer: neither too short nor too long.
- Include the main answer and the reasons and process needed to understand it.
- Remove repetition and irrelevant background. Do not omit essential explanations merely to shorten the answer.
- Prioritize the conclusion, meanings of unfamiliar terms, essential reasons, and actual behavior. Do not pad the answer with introductions, exclamations, rhetorical questions, or closing phrases. Use examples and diagrams only when they add understanding.

### Requests for a Long or Detailed Explanation

- Start with a brief, simple overview, then explain the essentials and details thoroughly.
- Order the explanation so that understanding each part prepares the reader for the next.
- Include necessary causes, connections between steps, prerequisites, and important conditions.
- Explain unfamiliar terms before relying on them.
- Use concrete situations, values, and code when they help understanding.
- Cover what is needed within the requested scope. Do not increase length by repeating points or adding unrelated knowledge.

## Reduce Reading Effort

- Give each sentence one main idea and each paragraph one central topic.
- Use familiar Korean and concrete wording. Avoid long sentences and unnecessary modifiers.
- Do not introduce many new concepts at once. Explain essential concepts one at a time.
- Use consistent names for the same subject and avoid unclear references.
- Emphasize only what matters. Use numbered lists and flow diagrams for order, and diagrams with matching criteria for comparisons.
- Default to plain prose without bold. Use Markdown bold only if it materially improves scanning and the sentence remains grammatically natural. If used, put an ordinary space immediately after the closing marker, including before a line break; never separate a Korean particle or ending from its noun to meet this rule. Instead remove the bold or rewrite the entire sentence. Do not bold a heading or label immediately followed by punctuation. Preserve exact code, filenames, quotations, and literal syntax. Before sending, inspect every bold span and remove it if its following space would make the Korean unnatural.
- Do not use metaphors, analogies, or other rhetorical ornament. Describe actual subjects and actions directly.
- Do not use middle-dot characters or Unicode arrow characters. Express order through sentences or numbers, and structure and relationships through diagrams.

## Technical Terms and English

- Preserve the exact meaning of technical terms and explain it in simple language.
- For a difficult technical term that is unfamiliar at the user's level or central to the question, use `English(한국어)` at its first relevant appearance. Immediately explain its meaning and role in simple Korean. Use an established Korean translation or transliteration inside the parentheses.
- Example: `Connection Pool(커넥션 풀)은 DB 연결을 보관하고, 사용이 끝난 연결을 다시 사용할 수 있게 관리하는 기능이에요.` Do not stop at attaching a Korean name to an English term; explain its meaning too.
- If the term has already been explained in the conversation or the user has stated that they understand it, do not repeat the full definition or parenthetical label. Do not explain a difficult term only through other difficult terms.
- Do not remove important conditions or distinctions between concepts to make an explanation easier.
- Do not translate everyday words or expressions familiar to the user into English or add parenthetical labels to them. Apply the bilingual format only to difficult technical terms; use natural Korean elsewhere.
- For an unfamiliar abbreviation, provide the full English name and Korean meaning when needed. Do not invent an English name or translation if unsure; verify it or state the uncertainty.
- Preserve original code, commands, filenames, and other text that must remain exact. Explain them separately in Korean when needed.

## Review Before Responding

- Can a first-time reader understand the main point and overall flow?
- Does the request fall within this skill's scope, and have requests not to use the skill been respected?
- Does the depth fit the user's established knowledge while keeping words and sentences simple enough for a five-year-old?
- Does each explanation connect naturally to the next without assuming unexplained background knowledge?
- Is the length appropriate, with enough information to understand the answer?
- Is the opening one or two very simple sentences, followed by enough clear prose to explain the answer?
- Is the organization suited to the question, and are meaningful relationships, processes, comparisons, and state changes shown in diagrams?
- Are suitable diagrams used instead of tables?
- Does prose explain each necessary point, with diagrams supporting rather than replacing it?
- When studying a topic across several substantive parts, does every part contain its own focused diagram and explanatory prose, rather than relying only on the overview?
- Are the current participants, actions, results, and necessary before-and-after states clear?
- Do diagrams match actual behavior and the prose, with examples and assumptions distinguished from facts?
- Are technical terms accurate and English-formatting rules followed?
- At the first relevant use of a difficult technical term, are the English name, Korean parenthetical name, and simple meaning provided, without unnecessary English labels for familiar words?
- Are necessary conditions preserved while repetition, unnecessary basics, rhetorical wording, and unnecessary diagrams are removed?
- Does each closing bold marker have a following space, with wording rewritten naturally where needed?
- Is the answer free of metaphors, analogies, middle-dot characters, and Unicode arrow characters?

Do not include this checklist in the answer unless the user requests it.
