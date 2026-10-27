# Diagram-supported explanations

Use this guide for processes, systems, comparisons, and state changes. The goal is for a reader to understand the whole subject and then learn the actual behavior in manageable parts. Do not turn every request into a fixed template.

## Start with the whole picture

1. Answer the question in one or two very simple sentences. State a necessary assumption if the answer otherwise misleads.
2. Introduce one concrete example and its participants. Give a small Mermaid overview of the relevant overall relationship; label the actual actions and conditions.
3. In prose, orient the reader to what the overview shows and why the relationship matters. Explain the details in its order. A short answer can use this overview plus prose without manufacturing steps.

## Teach the details

For a study request that develops a subject through multiple substantive parts, including an ordinary lesson, follow-up or deeper explanation, divide it into meaningful learning units. Explicit words such as "detailed" or "step by step" are not required. For each substantive unit, explain in prose what happens, why, and what follows, and place a focused diagram in that unit. The overview does not replace these diagrams. Each should show the current interaction, condition, or state before and after; retain unchanged values when they explain the outcome. Combine closely related actions into one unit only when they teach one idea. Do not make a diagram for an administrative heading. A one-sentence definition or an incidental short answer is not a multi-part lesson; do not invent parts for it.

### How to reduce the reader's workload

- Plan units around distinct questions the reader must understand, such as what changes in memory, what an UPDATE does, and what happens on commit or rollback. Use one familiar example and the same names and values throughout.
- Put each small diagram immediately after its introductory explanation or immediately before the prose that interprets it. Do not make the reader return to the overview to understand a later step.
- Show only the participants and values needed for the current idea. Include an unchanged value when it matters to understanding the change. Show a before and after, a request and response, or a conditional branch as appropriate; do not draw the step title alone.
- A code block is not a substitute for the focused diagram. Explain the code's important behavior in prose, then show its effect in the diagram; avoid repeating the code line by line.
- For example, in a JDBC lesson where Java changes a name before issuing UPDATE, a focused diagram can show Java's name changing from 민수 to 지수 while the DB remains 민수. A later focused diagram can show commit and rollback as alternative outcomes, with Java and DB values separately labeled. These are illustrative examples, not facts about a user's system.
- Keep each diagram small enough to read at once. If a unit has too many independent changes, split the learning unit and explain each one rather than hiding its details in the overview.

## When code helps

- Use code when it makes the requested implementation, method call, or concrete behavior easier to understand. Keep it focused on the current learning unit and use a complete example when necessary to show how the operation is actually performed. Do not add code just to satisfy a format.
- Introduce the example's setup and relevant initial values, then place the code, a focused diagram, and an explanation close together. Describe what each important statement receives, changes or requests, and produces. Explain unfamiliar syntax when needed, without narrating every line mechanically.
- In the diagram, use the same names and values as the code. Show which operation causes each change, which subject owns each value, and the relevant before and after state or request and response. Explain any important conditions or error paths in prose and diagrams as appropriate.
- Distinguish executable examples from excerpts and clearly mark placeholders, configuration requirements and assumed behavior. Do not claim the code was executed or represents the user's system unless verified. Preserve exact code and commands.

For comparisons, show the subjects under the same criterion in one focused diagram and explain their practical difference using the same concrete situation. For cause and effect, depict the intermediate change, not only the cause and final outcome. For stored or in-memory values, name their locations and show changed and unchanged values when relevant.

## Prose and diagram have different jobs

- The diagram shows who acts, what they act on, order, conditions, and resulting states. Keep its labels short and consistent.
- The text explains unfamiliar words, why each action matters, and how one result leads to the next. A reader should not need to infer the explanation from arrows alone.
- Keep the prose and diagram consistent. Mark invented values and assumptions as examples; do not imply unverified implementation details are facts.
- Use `sequenceDiagram` for requests and responses, `flowchart` for decisions and processing, and `stateDiagram-v2` for transitions. Choose another Mermaid form when it fits better. Use readable text diagrams if Mermaid is known not to render.

## Review the complete explanation

Follow one example from the initial state to the final result. Check that every substantive unit in a multi-part study explanation contains its own focused diagram and prose, that overview and detailed diagrams agree, and that important failure branches and conditions are not omitted. Combine truly duplicate units, not the prose or focused diagrams needed to understand them. Do not claim that a reader has understood without evidence.
