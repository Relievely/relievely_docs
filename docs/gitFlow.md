```mermaid
gitGraph
    commit id: "First" type: HIGHLIGHT tag: "RC_1"
    branch feature-1
    checkout feature-1
    commit
    commit
    commit
    commit
    branch hotfix-a
    checkout hotfix-a
    commit
    checkout feature-1
    merge hotfix-a
    branch hotfix-b
    checkout hotfix-b
    commit
    commit
    checkout feature-1
    merge hotfix-b
    branch sub-feature-1
    checkout sub-feature-1
    commit
    commit
    checkout feature-1
    merge sub-feature-1
    checkout main
    merge feature-1
    commit id: "Second" type: HIGHLIGHT tag: "RC_2"
```
