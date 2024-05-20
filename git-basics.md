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

  h2, h3, h4, h5, h6 {
    opacity: .9;
  }

  ul, li {
    text-align: left;
    margin-left: 0;
  }
---
# Git Fundamentals
### What are Git objects?

---
## What are Git objects?

<br/>

---
## What are Git objects?

They're files.

<br/><br/><br/><br/><br/><br/><br/>

---
### Where are Git objects located?

---
### Where are Git objects located?

They're in the `.git` directory.

```
.git/
  objects/💁‍♂️
  ...
app/
build.sbt
```

---
### Demo time!

Create a fresh repo:
```bash
rm -r my-test-repo;
git init my-test-repo;
cd my-test-repo;
```
Output:
```text
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint:   git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint:   git branch -m <name>
Initialized empty Git repository in /Users/dan.silaghimercator.group/fs/proj/local/git-fundamentals-marp/my-test-repo/.git/
```

---
### Demo time! (Step 2)
⚠️ In a terminal window you won't use for work ⚠️,
set the following environment variables:
```bash
export GIT_AUTHOR_NAME='Author';
export GIT_AUTHOR_EMAIL='some@email';
export GIT_COMMITTER_NAME='Author';
export GIT_COMMITTER_EMAIL='some@email';

export GIT_AUTHOR_DATE='2005-04-07T22:13:13+0000';
export GIT_COMMITTER_DATE='2005-04-07T22:13:13+0000';

export PS1="GIT DEMO ONLY: %1~: "; # To give you a warning in the terminal prompt.
```
This will force all commits to have the same dates/email.

