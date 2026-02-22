<%*
const arcType = await tp.system.suggester(
    ["Traditional — setup to payoff", "Tragedy / Downfall", "Event / Transition"],
    ["traditional", "tragedy", "event"],
    false,
    "What type of arc is this?"
);
if (tp.file.folder() !== "Arcs") {
    await tp.file.move("Arcs/" + tp.file.title);
}
-%>
---
title: <% tp.file.title %>
description: Outline for the <% tp.file.title %> arc
tags:
  - outline
  - Arc
aliases: []
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
publish: false
status: <% await tp.system.suggester(["Planned", "In Progress", "Complete"], ["Planned", "In Progress", "Complete"]) %>
enableToc: true
---
# <% tp.file.title %>

%% One sentence: what must change or be decided by the end of this arc? Every scene here should serve that goal. %%

## Arc Overview
- **Type**: <% arcType %>
- **Protagonist**: [[]]
- **Antagonist/Obstacle**: [[]]

## Structure
<%* if (arcType === "traditional") { -%>
%% Traditional arcs run setup → escalation → resolution. Every act should raise what is at stake. %%

### Act 1 — Setup
%% Establish the status quo before everything changes. The reader needs to understand what is normal before it gets threatened. %%
- **Status Quo**: %% What does normal life look like for these characters going into the arc? %%
- **Inciting Incident**: %% The event that makes the status quo impossible to return to and forces the protagonist to act. %%
- **Key Scenes**: [[]]

### Act 2 — Confrontation
%% The longest part. The protagonist pursues their goal and keeps running into escalating problems. %%
- **Rising Action**: %% What complications pile pressure on the protagonist? %%
- **Midpoint**: %% The pivot point halfway through — a revelation, betrayal, or the moment the protagonist shifts from reactive to proactive. Everything that came before now reads differently. %%
- **Darkest Moment**: %% The low point just before the climax. The protagonist seems beaten, or is forced to face their flaw directly. Makes the climax feel earned. %%
- **Key Scenes**: [[]]

### Act 3 — Resolution
%% Pay off everything planted in Acts 1 and 2. %%
- **Climax**: %% The final confrontation where the arc's central conflict is decided. No more delays. %%
- **Falling Action**: %% The immediate aftermath — what is the cost? What has changed, and for whom? %%
- **Resolution**: %% The new normal. What does the world look like once the dust settles? %%
- **Key Scenes**: [[]]
<%* } else if (arcType === "tragedy") { -%>
%% Tragedy arcs end in loss or irreversible cost — but the beats leading there still need to feel earned. The reader should see the fall coming and be unable to stop it. %%

### Act 1 — Setup
%% Establish what this character has and what they stand to lose. The reader needs to care before it is taken away. %%
- **Status Quo**: %% What does normal look like? What are the stakes before everything goes wrong? %%
- **Inciting Incident**: %% The event that sets the character on a path they will not be able to walk back from. %%
- **Key Scenes**: [[]]

### Act 2 — Descent
%% The character makes choices that accelerate their downfall, often believing they are doing the right thing. Irony is your friend here. %%
- **Rising Action**: %% What decisions or pressures push the character deeper in? %%
- **Point of No Return**: %% The moment the character could have turned back but did not — or genuinely could not. %%
- **Key Scenes**: [[]]

### Act 3 — Downfall
%% The consequences arrive. Do not soften them. A tragedy that flinches is not a tragedy. %%
- **Climax**: %% The moment the arc's central tension breaks — usually badly. %%
- **Cost**: %% What is lost? Be specific — a person, a belief, a future. %%
- **New Reality**: %% What does the world look like after? Who is left, and what do they carry? %%
- **Key Scenes**: [[]]
<%* } else { -%>
%% Event / Transition arcs do not need a three-act payoff — they chronicle something that happens and how the world changes because of it. Think: a timeskip, a journey, an off-screen war, a period of recovery. %%
- **What Triggers This**: %% What causes this period or event to begin? %%
- **Key Moments**: %% Snapshots of what happens during this stretch. %%
- **Immediate Aftermath**: %% How does the world look right after? %%
- **Long-Term Change**: %% What is permanently different because this arc happened? %%
<%* } -%>

## Conflict & Stakes
- **Central Conflict**: %% Person vs. person / self / world / system. What is the arc actually fighting over? %%
- **Stakes**: %% What happens if the protagonist fails? Aim for something personal AND larger-scale. %%
- **Obstacles**: 

## Themes
%% What ideas does this arc explore? (grief, power, trust, ambition, etc.) Themes should emerge from the conflict naturally, not be stated outright. %%
- 

## Character Development
%% Who changes in this arc and how? Even a small shift counts. %%
- **Changes**: 
- **Lessons Learned**: 

## Involved Characters
- [[Character A]]
- [[Character B]]

## Setting
- [[Location A]]

## Progress
- [ ] Outlined
- [ ] First Draft
- [ ] Revised
- [ ] Complete

## Notes
