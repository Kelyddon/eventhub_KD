```mermaid
gitGraph
   commit id: "init"
   branch dev
   checkout dev
   commit id: "setup husky + lint-staged"
   checkout dev
   checkout main
   merge dev tag: "v1.0.0"
```
