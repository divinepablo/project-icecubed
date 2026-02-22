<%*


let base = undefined;
if ((await tp.system.suggester(["Derived/Evolved Technique", "Original"], ["based", "new"])) == "based") {
	const folder = tp.app.vault.getFolderByPath("Power System/Techniques");
	console.log(folder);
	const names = folder.children.map(child => child.name.replace(".md", "")).filter(name => name != tp.file.title);
	console.log(names)
	base = await tp.system.suggester((item) => item, names, true, "Base technique");
}

if (tp.file.folder() !== "Techniques") {
    await tp.file.move("Power System/Techniques/" + tp.file.title);
}
-%>
---
title: <% tp.file.title %>
description: "IPS Technique: <% tp.file.title %>"
tags:
  - Technique
  - IPS
aliases: []
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
publish: false
enableToc: true
---


<%* if (base === undefined) { -%>
%% What does this technique look like when it fires? What is the first image it creates for a reader or viewer? %%

> [!abstract]
> 
## Mechanics
%% Every technique was defined through meditation — a "conversation" with the user's inner IPS deity. The deity names it. If two people independently define the same technique with zero variation, they get the same name. %%
- **[[IPS Energy]] Cost**: %% Low / medium / high, or a rough reserve number if you have one. %%
- **Actions Required**: %% Hand signs, verbal chant, physical trigger. Each action is shed as the technique gets more practiced. %%
- **Conditions**:

## Effects
%% What does the technique actually do? Be specific about range, duration, and what it physically interacts with. %%
- 
<%* } else { -%>
## Variant of [[<% base %>]]
%% Techniques can have souped-up versions that require new actions and/or conditions for a stronger effect (think Gojo's Hollow Purple needing a new chant). Leave blank if none exists yet. %%
- New [[IPS Energy]] Cost: 
- **Additional Actions**: 
- **Additional Conditions**: 
- **Enhanced Effect**: 
<%* } -%>
## Known Users
- [[Character A]]

## Related Techniques
%% Any techniques this one evolved from, counters, or pairs well with? %%
<%* if (base !== undefined) { -%>
- [[<% base %>]]
<%* } -%>
- 
## Notes
