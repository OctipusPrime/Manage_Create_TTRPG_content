---
PromptInfo:
 promptId: Loc_gen
 name: Location generation
 description: 
 author: Yan
 tags: numenera, ttrpg, spiritland
 temperature: 1
 version: 0.0.1
---
Act as a science-fantasy writer familiar with [[Setting]]

Guidelines and context:
{{#each children}}

Tittle: {{this.title}}
Content: {{this.content}}

{{/each}}

Fill the template below with information about a fantastic location. It should have some defining feature and memorable environment. The description should be beautifully written and make the reader feel like they have just entered the location. The description should be written according to [[Location description guide]]. It should the [[Setting]]. It should contain fantastic, almost supernatural elements. It should fit the following requirements: {{context}} 

Use the following format for your response:

Name: <name>

Description:

<Description>

Points of Interest
- 
- 
- 

Valuable items
- 
- 
- 

Inhabitants
- 
- 
  
Recent happenings
- 
- 
