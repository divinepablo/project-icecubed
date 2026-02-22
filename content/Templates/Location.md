<%*
const locationType = await tp.system.suggester(
    ["Town", "City", "Village", "Region", "Landmark", "Cavern"],
    ["Town", "City", "Village", "Region", "Landmark", "Cavern"]
);
const isSociety = ["Town", "City", "Village", "Region"].includes(locationType);
if (tp.file.folder() !== "Setting") {
    await tp.file.move("Setting/" + tp.file.title);
}
-%>
---
title: <% tp.file.title %>
description: "<% tp.file.title %> location in the IPS world"
tags:
  - Location
  - <% locationType %>
aliases: []
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
publish: false
enableToc: true
---
# <% tp.file.title %>

%% What feeling does this place give a reader? What is the first image that comes to mind? %%

> [!abstract]
> 

<%* if (isSociety) { -%>
## Overview
- **Founded**: %% Rough era or year. The Age of Enlightenment was ~350 years ago for reference. %%
- **Governing Body**: %% Who runs things here? A clan, a council, a single leader? %%
- **Population**: %% Dense city, small village, uninhabited ruin? %%
- **Economy**: %% How do people survive here? Trade, agriculture, IPS services, warfare? %%

## IPS Presence
%% IPS shapes every society in this world — how prominent is it here? Is there an academy, a dominant technique style, a famous lineage? %%
- **IPS Culture**: 
- **Techniques Native to This Area**: 
- **Notable Practitioners**: [[]]

## Notable Features
%% Landmarks, buildings, natural features — the things a traveler would notice or remember. %%
- 

## Inhabitants & Factions
%% Who calls this place home? Any power struggles, clan dominance, or social divides? %%
- 
<%* } else { -%>
## Description
%% Landmarks, ruins, and natural formations — describe the physical reality. %%
- **Physical Form**: %% What does it look like? Scale, material, atmosphere. %%
- **Scale**: %% How large is it? Describe relative to something familiar. %%
- **Age / Origin**: %% Was this formed naturally or by someone? Does it predate the current era or the Age of Enlightenment? %%

## IPS Presence
%% Some landmarks were formed by or infused with IPS energy. Does anything about this place feel unnatural or hostile to IPS use? %%
- **IPS Anomalies**: 
- **Notable Practitioners Who Visited**: [[]]

## Dangers
%% What makes this place hazardous or challenging to traverse? Hostile inhabitants, unstable terrain, IPS interference? %%
- 
<%* } -%>

## Narrative Role
%% Why does this location matter to the story? What major events happen here, and what does the place represent thematically? %%
- **Key Events**: 
- **Nearby Locations**: [[]]
<%* if (isSociety) { -%>
- **Notable Residents**: [[]]
<%* } else { -%>
- **Notable Visitors**: [[]]
<%* } -%>
