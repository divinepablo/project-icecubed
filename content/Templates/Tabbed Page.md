<%*
// Prompt for tab names, then build the full tab HTML
const tabInput = await tp.system.prompt(
    "Tab names (comma-separated)",
    "Overview, Details, Notes"
);
const tabNames = tabInput ? tabInput.split(",").map(t => t.trim()).filter(Boolean) : [];
if (tabNames.length === 0) {
    new Notice("No tab names provided — template aborted.");
    return;
}

const nav = tabNames.map((name, i) =>
    `    <button class="tab${i === 0 ? " active" : ""}" role="tab" aria-selected="${i === 0}" aria-controls="tab-${i + 1}">${name}</button>`
).join("\n");

const panels = tabNames.map((name, i) =>
    `<div class="tab-content${i === 0 ? " active" : ""}" id="tab-${i + 1}" role="tabpanel" aria-label="${name}">\n\n<!-- ${name} content here -->\n\n</div>`
).join("\n\n");
-%>
---
title: <% tp.file.title %>
description: ""
tags: []
aliases: []
created: <% tp.file.creation_date() %>
lastmod: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
publish: false
enableToc: false
---

<div class="tabs-wrap">
<div class="tabs-nav" role="tablist">
<% nav %>
</div>

<% panels %>
</div>

<style>
.tabs-wrap { margin: 1.5rem 0; }
.tabs-nav {
  display: flex;
  flex-wrap: wrap;
  gap: .25rem;
  border-bottom: 2px solid var(--lightgray, #e0e0e0);
  margin-bottom: 1rem;
}
.tabs-nav .tab {
  background: none;
  border: none;
  border-bottom: 3px solid transparent;
  margin-bottom: -2px;
  cursor: pointer;
  padding: .45rem 1rem;
  font-size: .9rem;
  color: var(--darkgray, #666);
  transition: color .15s, border-color .15s;
}
.tabs-nav .tab:hover { color: var(--secondary, #ff9100); }
.tabs-nav .tab.active {
  color: var(--secondary, #ff9100);
  border-bottom-color: var(--secondary, #ff9100);
  font-weight: 600;
}
.tab-content { display: none; padding: .25rem 0; }
.tab-content.active { display: block; }
</style>

<script>
// Each .tabs-wrap must contain: a .tabs-nav with .tab buttons, then .tab-content
// divs as its direct children (in the same order as the buttons).
document.querySelectorAll('.tabs-wrap').forEach(function (wrap) {
  var btns = Array.from(wrap.querySelectorAll('.tabs-nav .tab'));
  var panels = Array.from(wrap.querySelectorAll(':scope > .tab-content'));
  btns.forEach(function (btn, i) {
    btn.addEventListener('click', function () {
      btns.forEach(function (b) {
        b.classList.remove('active');
        b.setAttribute('aria-selected', 'false');
      });
      panels.forEach(function (p) { p.classList.remove('active'); });
      btn.classList.add('active');
      btn.setAttribute('aria-selected', 'true');
      panels[i].classList.add('active');
    });
  });
});
</script>
