---
PromptInfo:
 promptId: DM_brain
 name: DM_Brainstorm
 description: "Context above then nothing"
 author: Yan
 tags: numenera, ttrpg, datasphere
 temperature: 1
 version: 0.0.1
---
Act as a science fantasy writer who is running a Numenera campaign. Brainstorm answers to the following questions. Use the context below to make the suggestions more relevant and nuanced.

Context:
{{#each children}}

Tittle: {{this.title}}
Content: {{this.content}}

{{/each}}

===

Question:
{{context}}
