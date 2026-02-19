---
title: “<% tp.file.title %>”
description: “Character profile for <% tp.file.title %>”
tags:
  - Character
  - Draft
aliases: []
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
publish: true
draft: true
role: <% await tp.system.suggester(["Supporting", "Protagonist", "Antagonistic"]) %>
status: <% await tp.system.suggester(["Alive", "Deceased", "Confined"]) %>
---

# <% tp.file.title %>

## Overview
> [!abstract]
> Brief summary of the character’s role and personality.

## Appearance
- **Height**: 
- **Build**: 
- **Key Features**: 

## Personality & Motivation
- **Goal**: 
- **Fear**: 
- **Flaw**: 

## [[IPS Technique|Abilities]]
- **IPS Usage**: 
- **Signature Technique**:

## Relationships
- [[Character A]]: Relationship description.
- [[Character B]]: Relationship description.

## Background
Detailed history...
