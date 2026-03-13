---
layout: default
title: 適用しているスタイル
---

# 適用しているスタイル

```css
:root {
  --slidev-theme-font: "Yu Gothic UI", "Meiryo UI", sans-serif;
  --slidev-code-font: "Consolas", "Cascadia Mono", monospace;
  --template-accent: #0f5c4d;
  --template-accent-soft: #dceee8;
  --template-border: #b7d2c8;
  --template-footer: #24433b;
}

.slidev-layout {
  font-family: var(--slidev-theme-font);
  line-height: 1.5;
}

table {
  font-size: 0.9em;
}

.template-shell {
  position: relative;
  min-height: 100%;
  padding-top: 2.4rem;
  padding-bottom: 3.4rem;
  padding-left: 1.2rem;
  padding-right: 1.2rem;
}

.title-band {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: space-between;
  padding: 0.45rem 1rem 0.55rem;
  background: linear-gradient(90deg, var(--template-accent) 0%, #2b7a68 100%);
  color: #ffffff;
  font-size: 0.8rem;
  font-weight: 700;
}

.footer-band {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  display: grid;
  grid-template-columns: 1fr auto auto;
  padding: 0.55rem 1rem;
  background: var(--template-footer);
  color: #f6fbf9;
  font-size: 0.74rem;
}

.page-no {
  min-width: 4.4rem;
  padding: 0.15rem 0.55rem;
  border: 1px solid rgba(255, 255, 255, 0.35);
  border-radius: 999px;
  font-weight: 700;
}
```