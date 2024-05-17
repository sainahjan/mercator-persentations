---
# https://marpit.marp.app/directives
marp: true

paginate: true
theme: uncover
style: |
  /* https://github.com/marp-team/marp-core/blob/main/themes/uncover.scss */
  :root {
    --color-background: #ddd;
    --color-background-code: #ccc;
    --color-background-paginate: #dadada;
    --color-foreground: #345;
    --color-highlight: #9ac;
    --color-highlight-hover: #aaf;
    --color-highlight-heading: #9ac;
    --color-header: #bbb;
    --color-header-shadow: transparent;
  }
  section:has(:not(h1,h2,h3,h4,h5,h6)) {
    text-align: left;
  }
  
  /* Make first headings left-aligned.
   * Taken from (with some generalisations):
   * https://github.com/orgs/marp-team/discussions/478#discussioncomment-7179321
   */
  section:has(> :not(h1,h2,h3,h4,h5,h6)) > :first-child {
    flex: 1 0 auto;
    padding: 0;
    margin: 0;
    order: -999999;
  }
  section:has(> :not(h1,h2,h3,h4,h5,h6))::before {
    flex: 1 0 auto;
    display: block;
    content: '';
    order: 999999;
  }
---
# Git Fundamentals
## Git objects

---

