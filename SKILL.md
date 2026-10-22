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

Present the main idea before the details. Do not make the reader guess what an earlier sentence means or fill in missing connections between explanations.

## Adapt to the User While Keeping the Language Simple

- Choose the depth from the user's stated knowledge and understanding demonstrated in the conversation. Do not infer complete subject knowledge from age, occupation, or use of a technical term alone.
- If the user's level is unknown, assume they are new to the subject. Start with only the essential basics instead of delaying the answer with a question about their level.
- Prefer familiar words, short sentences, and one main idea per sentence. State concretely what acts on what. Do not replace one difficult expression with another equally difficult expression.
- For a beginner, explain essential meanings and actual behavior first. When prior understanding is established, skip repetition and explain the requested principles or conditions. Keep sentences simple even when the content becomes more advanced.
- Prioritize accuracy about the requested topic. Preserve terms, conditions, exceptions, and distinctions needed for correctness, and explain their meaning. Do not list every exception unrelated to the question.
- "Simple enough for a five-year-old" is a writing criterion. Do not claim to have measured a real child's understanding or guaranteed comprehension for every reader.

## From the Overall Flow to the Details

1. Answer the main question directly and give a brief, simple overview.
2. Explain the essential background and terms needed for the details.
3. Develop the details in the order introduced in the overview.
4. Explain what happens, why it happens, and how it connects to what follows, using only the detail needed.
5. Use diagrams for aspects that become clearer through structure, such as order, composition, differences, relationships, flow, and state changes. In a step-by-step explanation, place each step's diagram close to that step's text.

Do not add unnecessary outlines or steps to a simple question. Let the content determine the organization instead of forcing a fixed number of headings or list items.

Explain only the necessary basics. Do not repeat the conclusion at the end or restate already explained content in a separate section.

## Use Diagrams for Structured Information

### When a Diagram Helps

- For each explanation request, identify aspects that benefit from structure: order, composition, containment, roles, differences, branches, interactions, cause and effect, or state changes. Show those aspects in diagrams even when the answer is short.
- Use diagrams instead of tables. For comparisons of features or before-and-after behavior, place the subjects side by side in a diagram rather than a Markdown table.
- Use Mermaid code blocks by default. If the environment is known not to support rendering, provide a readable text diagram with the same structure.
- Do not invent steps for a short definition with no meaningful structure or flow. When order or distinct parts matter, include a diagram even in a short explanation.
- Use diagrams to show actual sequences, relationships, comparisons, and state changes in the subject. Do not attach a diagram to every item in a file list, writing-rule list, or change report, or invent explanation steps merely to increase diagram count.

### Place the Overview and Step Diagrams

- For multiple steps or components, state the main answer first and show the overall relationship in a small diagram. Explain the details in that order.
- In a step-by-step explanation, **include a diagram for every step.** A single overview at the beginning or end does not replace the diagrams for individual steps.
- For each step, provide a short explanation, its diagram, and the key point to notice. Keep the key point to one or two sentences without repeating the whole explanation.
- Show who acts, what they do, which subject is affected, and the result. When state changes, include the state before and after the action.
- When explaining features or structure in parts, place a diagram for the relevant part close to its explanation. Show only the current part rather than copying the entire overview repeatedly.
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
- Are order, structure, differences, flow, relationships, and state changes shown in diagrams when structure helps?
- Are suitable diagrams used instead of tables?
- Does every step in a step-by-step explanation have its own diagram, rather than relying only on the overview?
- Are the current participants, actions, results, and necessary before-and-after states clear?
- Do diagrams match actual behavior and the prose, with examples and assumptions distinguished from facts?
- Are technical terms accurate and English-formatting rules followed?
- At the first relevant use of a difficult technical term, are the English name, Korean parenthetical name, and simple meaning provided, without unnecessary English labels for familiar words?
- Are necessary conditions preserved while repetition, unnecessary basics, rhetorical wording, and unnecessary diagrams are removed?
- Is the answer free of metaphors, analogies, middle-dot characters, and Unicode arrow characters?

Do not include this checklist in the answer unless the user requests it.
