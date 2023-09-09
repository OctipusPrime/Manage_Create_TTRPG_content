---
PromptInfo:
 promptId: GM_GPT_NPC_gen
 name: GM_GPT_NPC_gen
 description: ...
 author: Yan
 tags: ttrpg
 temperature: 1
 version: 0.0.1
---
Act as a brilliant fantasy writer familiar with [[Setting]]. 

Guidelines and context:
{{#each children}}

Tittle: {{this.title}}
Content: {{this.content}}

{{/each}}

Given a Dungeons and Dragons table top rpg setting, fill the following template with information about a non-player character according to [[Angry GM NPC guide]]. They should fit the following description/requirements: {{context}}

Name:

Visual description:

Humanizing traits
1. 
2. 

Mannerism:

Want/Goal: 

Fear:

Backstory:

Weakness:

Special abilities/items given DnD 5e system
- 
- 