# Manage and Create TTRPG content
Obsidian templates for managing a table top rpg game and generating content using GPT.

## Installation
The "Example Vault" contains TTRPG folder with the prepared management system you can simply drop into your vault and start using. The Templates folder contains simple templates you can place into the folder where you store your other templates and the Text_Generator contains templates specific to the [Text Generator plugin](https://text-gen.com). If you want to use these, you need to download the plugin and specify path in the setting to this folder. 

### **Warning:** 
Due to Dataview not working well with canvas files you cannot SIMPLY rename the campaign. The name is spelled out in every single dataview query on the canvas so you will need to change it. Example:
Current link to the canvas is `[[Campaign.canvas|Campaign]]` and a dataview query for the adventures looks like this:
```
table without id file.link as "Name", description as "Description" From "TTRPG" or "Inbox"
and [[Campaign.canvas|Campaign]]
where contains(type, "adventure") and !completed sort file.name
```
So if you rename your campaign to "The Mighty Nein" (by changing the name of the canvas files) all the other links in the vault such as those in Templates are updated, but those in the dataview queries inside the canvas are NOT. So you need to go through all of them and change `[[Campaign.canvas|Campagin]]` to `[[The Mighty Nein.canvas|The Mighty Nein]]`. So the new query will look like this:
```
table without id file.link as "Name", description as "Description" From "TTRPG" or "Inbox"
and [[The Mighty Nein.canvas|The Mighty Nein]]
where contains(type, "adventure") and !completed sort file.name
```
If you find a workaround, please let me know. 



## Part 1: Managing a TTRPG campaign in Obsidian

This is how I used to manage my game notes and prep:
![GM note in GoodNotes](https://github.com/OctipusPrime/Manage_Create_TTRPG_content/assets/77053094/09882781-c543-49c5-a720-efd76f5aef90)

All hand written on my beloved iPad, a mindmap for locations, characters and items with notes, images and sketches about what might happen during the session. It worked well... as long as the adventures were straight forward, but fell apart once the players started coming to the same spots again and again, events played off of each other and plot thickened. I needed something more robust and expandable, thus I began to use [Obsidian](https://obsidian.md) and with the introduction of canvas created this:
![Canvas view of Purge](https://github.com/OctipusPrime/Manage_Create_TTRPG_content/assets/77053094/e8acc7bb-38c9-400d-beac-ebcc5bdddeac)

The basic format is as follows: Campaign is broken down into adventures where every adventure has a number of scenes to it. Campaign can easily last years in real life and is mostly bound by an overarching theme or a primes and has a stable setting with usually the same cast of player characters. Adventure is a single narrative with one more mysteries/decision for player to go explore and lasts up to a few months irl. Scene is a short encounter the players experience in game ranging from them overhearing a conversation to a session long boss battle.

In the active adventures I keep an overview of all concurrent adventures the party is involved in and aren't closed yet. I try to have up to 5 open adventures at a time because after that even I start losing track of what is going on. 

Below are **unresolved scenes**. I obviously don't plan every minute of every game, but I found it useful to think of adventures of consisting of scenes in which the characters are confronted with some information or forced to make a decision. Again, the scale varies, sometimes a scene is some off hand remark a passerby makes, other times it is an introduction of an NPC that will share vital information, yet another time it might be a battle that breaks out around the PCs. Scenes can last full evenings, but usually take place during a few in game minutes, again, it depends. I **never plan all the scenes** in an adventure ahead of time. I try to put as much agency and choice on the players and let them decide where the adventure will go.

Then we come to the **Follow up on** tab. Here I write all the relevant bits that came up during the sessions and I would like to come back to. In this campaign the players stole 300 credits from a powerful figure, reached out to an alter ego of a NPC they are doing a quest for and didn't resolve a conflict between two factions in the previous adventure. All of these will have an impact on future events and can themselves spawn adventures of their own. It is things like these that in my opinion make a game come alive and make you feel like it is a real place. I play [[DnD]] because of the choices I am forced to make and the consequences that come out of them. Having your choices bite you in the ass or help you out in a pinch is what the whole hobby is about. 

Final tab in the left column is an **Incubator**. Here I throw all the bits and pieces of ideas that I have and let them sit around until they come in handy while doing prep x months later. 

In the **Opening** tab I write whatever I want to start the session with. It can be a strong  scene which throws everyone into the game or bookkeeping - some important information I want to remind the players of. Sometimes I write the opening scene in prose, other times just jot down a few ideas and make the description on the fly. 

A little side-note: Recently I have come to appreciate how the lack of pre-written descriptions can actually enhance the game. It is fine when it is the beginning of a session, but I have found that players seem disappointed when they see me reading out a prepared description. I guess it is from knowing that they were "supposed" to do this rather than that they got there without me setting it up. 

The **Coming up** tab contains all of the scenes, characters, notes and whatever else that will likely come up that session. I rarely go through everything, so it stays until the next session or is scrapped if it became irrelevant. 

In **Secrets** I was inspired by the [Lazy Dungeon Master books](https://slyflourish.com/lazydm/). They function as little bits of information that can be revealed in order to advance the adventures. Here I write pieces information about the world that don't lend themselves into prepared scenes and give them out when the player are poking and prodding the world for info. This is the strength of these secrets: They can be found wherever the players look. 

**Backlog** is just what your would expect it to be. A record of most of the things that have happened in previous sessions. I write them in short sentences of who did what, where and why. Wiki Obsidian links are fantastic here since whatever note I open, I can immediately see how it came up during the sessions. 

**Player Characters** have a prominent spot since the story revolves around them. In the PC notes I keep track of the abilities and items that the players have at their disposal. Any time I struggle to come up with a challenge, I just browse their sheets and soon figure out a challenge that can be easily resolved with one of their tools. Often they use a different way, which is wonderful, but I found this way to both utilise less universal abilities and spark ideas for new encounters. 

Then there is a long list of NPCs, locations, monsters and so on. These are pulled from all over the Obsidian vault with [Dataview](https://github.com/blacksmithgu/obsidian-dataview) queries. The template that I am using for them are variations on:
```
---
alias: 
type: 
description: "" 
---
Campaign::
Adventure::
Location::
```
Followed by another [[Dataview]] query that displays all other notes of this format that link to that particular note.
```
table type as "Type", description as "Description"
from [[]] and ("TTRPG" or "Inbox")
```

The type can be an item, NPC, monster, location... whatever you need for your game. The Campaign and Adventure then allow for better display on the main canvas.

## Part 2: Using [[GPT]] to generate TTRPG content

I enjoy GMing the most when I feel like I have enough content for the players. Writing the prep can be fun, but coming up with 3 hours of content every week gets draining fast. That is why I started to use the Text Generator plugin to offload some of that workload. Here is an example: 
```
Act as a science fantasy writer familiar with the Numenera Datasphere. 

Guidelines and context:
{{#each children}}

Tittle: {{this.title}}
Content: {{this.content}}

{{/each}}

Given a Numenera table top rpg setting, fill the following template with information about a non-player character according to [[Angry GM NPC guide]]. They should fit the [[Datasphere]]. They can be either a voice, a transcribed physical being, a daemon (small AI) or a purely digital being. Their fear must be different from their want.  They should fit the following description/requirements: {{context}}

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

Special abilities given Cypher system
- 
- 

Items or trinkets they own
- 
- 
```

The `{{#each children}}` and so on part expands all the wiki links that are in considered context (more info on [Text Generator plugin](https://text-gen.com)). In the `{{context}}` I put whatever constraints I need the NPC to fit.

For example I need a NPC that informs the players that there is an upcoming Arena battle in the location and that someone called Zephyr is a crowd favourite. 
1. I open a new note and insert my NPC template with all the metadata already filled in. 
2. I write: "it needs to be a visitor to the [[Arena]] who has come to bet on the tournament. They are excited about the games and like to discuss their favourite, [[Zephyr]]" 
3. I run the "Generate and insert from template" action of Text Generator plugin with cursor on the line above

What happens here is that both the "Arena" and "Zephyr" notes together with "Datasphere" and "Angry GM NPC guide" notes are expanded into the context and are considered by GPT when writing a response. This is huge! You can just reference any other entity in your vault without having copy and paste all the details. What it spits out is a fully ready NPC with everything I need to run it that also fits precisely the situation that I need it in.

I have quite a few of these templates and they are available in this repo, yet still keep making more depending on what I happen to need. I change them as the setting or theme shifts and adjust as I see the [[LLM]] succeed or fail to meet my expectations. 

There you go, this is how I generate fleshed out content very quickly offloading all the annoying busy work and focusing on the grand story and tiny details, the things that I enjoy the most. It has allowed me to run adventures that I wouldn't have dared to run otherwise due to fear of their scale and thanks to the management system I feel on top of things even though there is drastically more text than I had with my old system. Thanks to how fast [[GPT]] is I can even generate stuff on the fly during the session.

I hope you enjoyed this rundown, hit the star if you did to show your appreciation. I will keep updating the templates and would love to see your own or how you modify them to fit your needs. Have fun gaming!
