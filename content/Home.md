---
created: 2026-03-14 20:55
---
| [[Categories]] | 

## Vault Rules 

- Avoid splitting content into multiple vaults
- Avoid folders for organisation
	- Vault root = Aethos 
	- References = everything I've taken from elsewhere ie. things I dont own / real-world info.
	- Glossary = my own definitions / understandings of terminology - update according to current understanding
- Avoid non-standard markdown 
- Always pluralize categories and tags 
	- Tags are for page status (incomplete, archived, evergreen, for-review, published etc)
	- Categories are for organising the pages by Aethorian standards (Places, Characters, Castles, Cities, Spells etc)
- Use internal links profusely 
- Use YYYY-MM-DD dates everywhere 
- Keep a single to-do list per week

#### Weekly To-Do 2026-03-09 

- [ ] Create [[Vault Style Guide]] for Wiki entries into the vault. What should be in the first sentence, what info to prioritise and in what order for each category etc.
- [ ] Decide on an Aethorian standard dating method - month names? hyphen separation? 
- [ ] Write about slaves and slavers in the serpent realms. 
- [ ] Make [[Region Template]] with .base for Locations in that region
- [ ] Make [[Places]] .base 
- [ ] Write section on focusing crystals & flight, for [[Dragonrock]]
- [ ] List all the people [[Gozlu]] ritually executed - he's in a lot of people's bad books for killing friends & family members.
- [ ] Find out the authority type of a feudal lord, like a Duke. is it still monarchy? is it just Feudal? 
- [ ] Make Item.base with option that will show the stats of the current page's item like weight, type, charges, etc. 
	- [ ] replace the dataview code for my homebrew items with those .bases
- [ ] Make a list of all tags (stub, published, important etc.)
- [ ] Are [[Siladrin]] just copyright-proof Drow or are they a specific drow ethnicity? 
- [ ] Dinstinguish between Religions and Faiths
- [ ] List all the [[Satraps of Kovith]] and add them to the list of leaders on the [[Free Cities of Kovith]] doc. 

## Style Guide 

### Frontmatter Properties

#### tags: 
Tags (either in-line or as a frontmatter property) are meta-info about a page's status and type.
- #wip - work in progress / incomplete. page is in the process of becoming either a stub or fully completed article. Either way, it needs more work before it can be published
- #stubs - a page containing limited or incomplete information on its subject
- #urgent - a page in need of update and review as soon as possible, usually because the prose or phrasing is poor or nonsensical and I couldnt be assed to solve it yet. 
- #archived - page contained outdated information or lore, but may still be useful as reference material. 

#### categories:
Categories should always be pluralised, and are used to determine a note's subject's type. 
- [[Places]] - a visitable site; a region, a settlement, a polity, a dungeon, a shrine, or any other such locatable position in space and geography. 
- [[Regions]] - Denotes a Place as being a large area, usually of land or sea, such a Kingdom might be, or an Ocean, or a plane of existence. 
- [[Polities]] - Geopolitical entities. Denotes a Place or Faction as having both geographical and political boundaries/borders, such as a Kingdom or a Satrapy or a Duchy or an Empire might. A polity is bounded not just by some physical feature like a river or mountain range, but also by the limit of its projected direct authority or governance - its sphere of influence, so-to-speak.
- [[Settlements]] - Populated community, eg. town, city, village
- [[Continents]] - Top-level landmass. 
- [[Factions]] - denotes page as being about a Faction. i.e. a group or organisation or political entity (or a sub-section of any thereof) able to make decisions and take action to achieve its goals. 
	- Yes, people/characters are basically micro-factions because they have agency and interests that they can act on. 
- [[Characters]] - Sentient beings? Individuals. Of all kinds. From Dragon to Goblin, if they have a name, they're a character. Sure. 

#### factions:
When listed as a frontmatter property and not as a Category, the Factions property denotes which Factions (pages with the Factions category) the page's subject belongs to. Factions cannot belong to themselves, though they can belong to other Factions.
- eg. if a region lists factions: [[Kingdom of Mercy]], then it shows that Mercy is the only faction with notable authority over that region. If a region lists factions: [[Church of The Last Day]], [[Kingdom of Mercy]], then it shows that both these factions have authority over that region in some way. 
- For Places with governments (like polities and settlements), even if its just a lord and his cronies, then that would be listed under the "leader:" property. 

#### location:
A frontmatter property only. Denotes the whereabouts - the place - of the page's subject. If the page's subject can be found in multiple Places, list all. Used exclusively in frontmatter (eg. location: [[Obsidian Coast]], [[Aethos]]). 

#### characters:
when used as a frontmatter property (eg. characters: [[Queen Anastasia Valencia II]]), denotes relevance to page's subject. For example, if the page is an event like a festival, then characters attending the festival may be listed on the event's page under the "characters:" property.
> - NB: this property may be redundant. 

#### leader:
denotes a character as the one in charge of / leading the page's subject (typically used on faction pages to denote the faction head) 

#### created:
date that the page was created. YYYY-MM-DD

#### authority: 
denotes the authority type by which a faction is governed. Eg. Constitutional Monarchy. Theocratic Oligarchy. Democratic Republic. etc. 



## Player Wiki 

GitHub Pages, Quartz, and GitHub Actions should allow for the selective publishing of repository files to an obsidian-wiki-style website via the frontmatter property "publish: true/false".

### Resolving Invalid Wikilinks for Published Files
When files are published, their internal wikilinks may no longer have valid destinations, because they are linking to unpublished files. This wont be an issue for DM's using obsidian to navigate the repo - only for players navigating the public wiki. In these cases, the link will return them an "error 404 page not found". 

**Stub Pages.** To resolve this, we can publish short stub pages for these "known-unknowns" pages - including only the limited information the players ought to be privy to. Denote stub pages using the tag "#stub". 

#### Custom Error 404 Page
We can also leave the links as broken but change the error 404 page to read as: 
	"The knowledge you seek resides within Forbidden Archive 404 - return to the public archives post-haste, lest the silent watchers be made aware of your attempted trespass."

| Claude tells me this is doable:                                                                                                                                                                                                                                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Yes — you can customise the 404 page directly by editing `quartz/components/pages/404.tsx` [Jzhao](https://quartz.jzhao.xyz/) in the Quartz repo. It's a simple React/JSX component, so swapping out the text is straightforward even without much coding knowledge.<br><br>Something like:<br><br><br>```<h1>Forbidden Knowledge</h1><br><p>custom message here</p>``` |
## Wiki Development Roadmap
> Grand Total (Phase 1 Core Build) ~40–45 hours

Phase 1 focuses on establishing the core structure of the Aethos wiki, providing a foundation for all later expansions and refinements. Time estimates are in **hours** of focused writing and editing work.

### 1. World Overview – Etharia

- [ ] Cosmology & astronomy write-up: 1–2 hours
- [x] Calendar page (months, weekdays, year length): 1 hour
- [ ] Seasons & orbital explanation: 0.5 hour
- [x] Severance summary block: 0.5 hour
- [ ] Planes overview page (with stubs for each plane): 2 hours
- [ ] Subpage Aethos (boundaries, realms, regions list): 3.5 hours

**Subtotal:** \~8 hours

### 2. History & Timeline

- [ ] Define eras & ages: 1 hour
- [ ] Draft unified timeline page: 2 hours
- [ ] Anchor events (Shaedhe Dynasty, Incidian conquest, Mercy founding): 2–3 hours
- [ ] Create stub pages for major events: 3 hours

**Subtotal:** \~8–9 hours

### 3. Pantheon Portal

- [x] Theology overview: 1 hour
- [x] Pantheon index with table: 2 hours
- [ ] Standardize deity pages: 4–5 hours

**Subtotal:** \~7–8 hours

### 4. Key Regions

- [ ] Kingdom of Mercy page: 4–5 hours
- [ ] Empire of Phairos page: 3–4 hours
- [ ] Obsidian Coast / Kovith page: 3–4 hours
- [ ] Region template structure: 1 hour

**Subtotal:** \~12–14 hours

### 5. Linking & Integration

- [ ] Interlink realms, deities, and events: 4–5 hours

