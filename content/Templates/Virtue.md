<%*
const virtues = ["Chastity", "Temperance", "Charity", "Diligence", "Kindness", "Patience", "Humility"];

const folder = tp.app.vault.getFolderByPath("Character/Virtues");
const names = folder.children.map(child => child.name.replace(".md", "")).filter(name => name != tp.file.title && name !(name in virtues));
console.log(names)
let virtue = await tp.system.suggester((item) => item, names, true, "Virtue");
let metadata = {
	"Chastity": ["Purity, self-control, and respect for oneself and others in relationships.", "https://en.wikipedia.org/wiki/Chastity"]
	"Temperance": ["Moderation, self-restraint, and balance in all pleasures", "https://en.wikipedia.org/wiki/Temperance_(virtue)"]
	"Charity": ["Selfless love, compassion, and willingness to help others.", "https://en.wikipedia.org/wiki/Charity_(Christian_virtue)"]
	"Diligence": ["A strong work ethic, perseverance, and commitment to excellence.", "https://en.wikipedia.org/wiki/Diligence"]
	"Kindness": ["Empathy, compassion, and celebrating the good fortune of others.", "https://en.wikipedia.org/wiki/Kindness"]
	"Patience": ["The ability to endure difficult situations with grace, forgiveness, and mercy.", "https://en.wikipedia.org/wiki/Patience"]
	"Humility": ["Recognizing limitations and maintaining a modest, respectful attitude.", "https://en.wikipedia.org/wiki/Humility"]
}

if (tp.file.folder() !== "Virtues") {
    await tp.file.move("Characters/Virtues/" + tp.file.title);
}
-%>
---
title: <% tp.file.title %>
description: Malik Monk's clone embodying <% virtue %>
tags:
  - Character
  - Clone
  - Heavenly-Virtue
aliases:
  - Chastity
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date() %>
publish: false
draft: true
enableToc: false
virtue: Chastity
opposes: Lust
role: <% tp.system.promp %>
---

> [!abstract] Virtue
> <% virtue %>: <% metadata[virtue][0] %>

## Virtue — [<% virtue %>]( <% metadata[virtue][1] %>)

## Personality

## Combat Role

## Relationships
- [[Malik Monk]] — creator
