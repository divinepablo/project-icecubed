<%*
const hasGoal = await tp.system.suggester(
    ["Yes — has a defined goal", "No — not yet / not applicable"],
    [true, false],
    false,
    "Does this character have a defined goal?"
);
const includeCharArc = await tp.system.suggester(
    ["Yes — include Character Arc section", "No — skip it"],
    [true, false],
    false,
    "Include a Character Arc section?"
);
if (tp.file.folder() !== "Characters") {
    await tp.file.move("Characters/" + tp.file.title);
}
-%>
---
title: <% tp.file.title %>
description: "Character profile for <% tp.file.title %>"
tags:
  - Character
  - Draft
aliases: []
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
publish: true
draft: true
enableToc: true
role: <% await tp.system.suggester(["Supporting", "Protagonist", "Antagonistic"], ["Supporting", "Protagonist", "Antagonistic"]) %>
status: <% await tp.system.suggester(["Alive", "Deceased", "Confined"], ["Alive", "Deceased", "Confined"]) %>
arc: []
---
# <% tp.file.title %>

%% Who is this character at their core? What single sentence captures what they represent thematically? %%

> [!abstract]
> 

## Basic Info
- **Nickname(s)**: 
- **Age**: 
- **First Appearance**: [[]] %% Which arc or scene do they first show up? %%
- **Affiliation**: %% Village, clan, group, or loner? %%

## Appearance
- **Height**: 
- **Build**: 
- **Key Features**: 
- **Voice/Mannerisms**: %% How do they carry themselves? Speech patterns, posture, any tics? %%

## Personality & Motivation
<%* if (hasGoal) { -%>
- **Goal**: %% What do they want more than anything — short-term and long-term? %%
<%* } -%>
- **Fear**: %% What would stop them cold or genuinely break them down? %%
- **Flaw**: %% The flaw that creates real story problems, not just a personality quirk. %%
- **Strengths**: 
- **Defining Trait**: %% The one thing anyone who knows them would name immediately. %%

## [[IPS Technique|Abilities]]
- **[[IPS Levels|IPS Level]]**: %% 1–5, or Boundless. Reserve size determines technique power ceiling. %%
- **IPS Specialty**: %% What concept did they conceptualize? (electricity, fire, intangibility, etc.) %%
- **IPS Background**: %% Innate practitioner, learned late, self-taught? Affects starting reserve. %%
- **Signature Technique**: %% Their most defining move — name and brief effect. %%
- **Burned-In Techniques**: %% Techniques so practiced they activate with no actions. %%

## Relationships
%% Use [[wikilinks]] so the graph connects these nodes. %%
- 

<%* if (includeCharArc) { -%>
## Character Arc
%% How does this character change across the story? Even minor characters should shift in some meaningful way. %%
- **Starting Point**: %% Who are they when we first meet them? %%
- **Turning Point**: %% What event forces growth or doubles down on who they are? %%
- **Ending Point**: %% Where do they land by the end of their arc or the series? %%

<%* } -%>
## Background
%% Full prose or bullet points, whatever helps you write from their POV later. Include formative events, family, where they grew up, and why they are the way they are. %%
