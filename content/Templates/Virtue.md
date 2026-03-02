<%*
const virtues = ["Chastity", "Temperance", "Charity", "Diligence", "Kindness", "Patience", "Humility"];

const folder = tp.app.vault.getFolderByPath("Character/Virtues");
const names = folder.children.map(child => child.name.replace(".md", "")).filter(name => name != tp.file.title && name !(name in virtues));
console.log(names)
let virtue = await tp.system.suggester((item) => item, names, true, "Virtue");


if (tp.file.folder() !== "Virtues") {
    await tp.file.move("Characters/Virtues/" + tp.file.title);
}
-%>
---
title: <% tp.file.title %>
description: "Malik Monk's clone embodying Chastity Heavenly Virtues"
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
role: Nun
---

> [!abstract]
> A clone of [[Malik Monk]], derived to revolve entirely around **Chastity** — the mastery of desire and the preservation of absolute purity of purpose. She presents as a nun.

## Virtue — <% virtue %>

## Personality

## Combat Role

## Relationships
- [[Malik Monk]] — creator
