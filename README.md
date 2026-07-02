# Documenting AI-generated code commits
With ever-more program code created through generative AI,
it is important to document its provenance.
In industry this can help
diagnose the root cause of problems discovered long after the code was written,
locate issues with a similar cause,
and evaluate the cost and benefits of AI.
In educational settings it can help students be honest, mindful, reflective,
and transparent regarding their use of generative AI
and provide educators with data they can use
to evaluate objectively student work.

Given the variety of generative AI systems and approaches in current use,
it is typically difficult to obtain the usage metadata in a standardized form.
Therefore, developers should add appropriate headers at the end
each configuration management system (e.g. Git) commit message.

## Proposed headers
The following headers are proposed to be added in each commit message
where AI played a role.
Some can be omitted if they are not applicable or the data are not available.
More can be added if needed and elements can be adjusted based on availability
and local requirements.
The most important thing is consistency within each organization or
project.
As usual for headers, long text is wrapped and indented.

```yaml
AI-Tool: Name of employed IDE extension, chatbot, agent or other tool
AI-Model: Name of LLM used by the tool
AI-Task: Summary of prompts
AI-Prompt-1: First prompt
AI-Reasoning-1: Transcript of AI's reasoning process (often omitted)
AI-Response-1: First response (often omitted)
AI-Prompt-2: Second prompt
AI-Response-1: Second response
AI-Prompt-n: …
AI-Tokens: Comma-reparated list by token type
AI-Role: Comma-reparate list with one or more of the following: code-suggestion, code-transformation, code-generation, code-review, documentation, bug-fixing, explanation, design, analysis
```

## Example
```yaml
AI-Tool: OpenAI Codex
AI-Model: gpt-5.5 medium
AI-Task: Improve page layout
AI-Prompt-1: Add a small space below the title
AI-Response-1: I added the required space by changing the heading bounding box
AI-Prompt-2: Increase the space
AI-Response-2: I added the required space by changing the heading bounding box
  from 10 to 12 pixels
AI-Tokens: input=49283, cached=426368, output=2979, reasoning=607
AI-Role: bug-fixing, code-generation
```

## Implementation details
The headers can be added at the end of each commit message.
Alternatively, headers can be added as Git notes in the namespace `ai`
(command `git notes --ref=ai add …`)
to keep visible commit messages short.
Bots shall be configured to add these comments in all their commits.
Also some people may find ways to automate the process
of generating the required headers.
These will be referenced here.

## License
This document is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).
