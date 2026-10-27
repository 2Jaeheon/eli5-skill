# Explanation patterns

Use the relevant pattern, not every pattern. Start with the short plain-language answer required by SKILL.md. The rest of the answer should resolve the reader's actual question, not merely name the parts.

## Choose what the reader needs

- For a definition, say what it does and when it matters. Add an example only if the definition alone is hard to understand.
- For a process, choose one concrete situation. Explain who acts, what changes, and what happens next. Use numbered steps only when their order helps; connected paragraphs may be clearer.
- For a comparison, introduce the shared situation first. Describe each choice using the same relevant criteria, then explain the practical difference. Do not imply one approach is always better when the answer depends on conditions.
- For a why question, connect the cause to the outcome through the missing intermediate behavior. Explain the specific conditions under which the outcome follows, rather than presenting correlation as cause.
- For a how-to question, show the smallest usable example when it helps. Explain where the input comes from, what each important operation does, and what the reader can expect to observe. State setup assumptions and distinguish an illustrative snippet from verified project behavior.
- When the user asks how to perform an actual operation, make the example perform that operation rather than substituting a print statement or a placeholder. If a real operation needs credentials, dependencies, or a configured service, state them and provide an illustrative example without claiming it was executed. If a partial snippet is more appropriate, explicitly identify the omitted operation and what it would do.

## Make the explanation followable

- Use one consistent example and name each participant or value before using it. When a value changes, distinguish the original value, the new value, and where each is stored.
- Ensure example inputs select the described subject: for example, if SQL uses a specific ID, state which record has that ID. When explaining a later request, identify how the necessary value reaches the next participant if that mechanism matters to the question.
- Link neighboring sentences explicitly when the reason is not obvious. Explain why an action leads to the next result instead of just listing actions.
- Introduce an unfamiliar term at the point it becomes necessary, with its meaning in ordinary Korean. Do not introduce several related terms in advance or add another technology just to mention alternatives.
- If a statement depends on configuration, framework, timing, or a specific example, put that condition near the statement, including in the introduction when needed. Do not present a possible failure response as automatic when the program must explicitly perform it.
- For code, describe the important behavior in prose as well. A diagram or code block supports the explanation and does not replace it. Avoid repeating every line or putting the same sequence in prose, code, and a diagram without a reason.
- For existing code or systems, inspect the relevant source when available before calling behavior fact. Otherwise label the example or assumption and avoid claiming it was verified.

## Quick self-check using a concrete situation

Before responding, mentally follow the example from its starting condition to its result. Can the reader tell what caused the result, what changed, what stayed the same when relevant, and what the explanation assumes? Add a missing connection if needed. Remove an unnecessary term, diagram, or repeated explanation if it does not help answer the question.
