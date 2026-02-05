# File Nesting Test

This repository is a **sandbox** to test and demonstrate **file nesting rules**.
All files are organized per language or framework in separate folders to make testing easier.

---

## Purpose

- Quickly verify Neo-tree **nesting rules (`nesting_rules`)** in Neovim
- Test feature vs base file nesting behavior
- Serve as a reference for organizing project files for multiple languages and frameworks

---
## Expected Result

- **Docker**

    Expected nesting structure for Dockerfile:    
    ```bash
    Dockerfile
    └── .dockerignore
    └── Dockerfile.development
    └── Dockerfile.local
    └── docker-compose.development.yaml
    └── docker-compose.local.yaml
    └── docker-compose.yaml
    ```
---
- **Node**

    Expected nesting structure for Nodejs or Bun lock file:   
    ```bash
    package.json
    └── bun.lock
    └── bun.lockb
    └── package-lock.json
    └── pnpm-lock.yaml
    └── yarn.lock
    ```

---
## Common Rules

- **Neo-tree (Nixvim)**

Rules for grouping related files under their primary source file.
```nix
plugins.neo-tree.settings.nesting_rules = {
    "docker" = {
        pattern = "^dockerfile$";
        ignore_case = true;
        files = [
            ".dockerignore"
            "docker-compose.*"
            "dockerfile.*"
        ];
    };
    "node" = {
        pattern = "^package%.json$";
        files = [
            "package-lock.json"
            "yarn.lock"
            "pnpm-lock.yaml"
            "bun.lockb"
            "bun.lock"
        ];
    };
};
```

---
## Other Rules
- [Go](./go/RULE.md)
- [Java](./java/RULE.md)
- [JavaScript](./javascript/RULE.md)
- [Python](./python/RULE.md)
- [Rust](./rust/RULE.md)
- [TypeScript](./typescript/RULE.md)

