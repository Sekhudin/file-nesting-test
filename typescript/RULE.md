## Expected Result

- **TypeScript**

    Expected nesting structure for a TypeScript-based project:    
    ```bash
    foo.ts
    ├── foo.d.ts
    ├── foo.type.ts
    ├── foo.interface.ts
    ├── foo.spec.ts
    ├── foo.test.ts
    ├── foo.e2e-spec.ts
    └── foo.e2e-test.ts
    foo-bar.ts
    ├── foo-bar.d.ts
    ├── foo-bar.type.ts
    ├── foo-bar.interface.ts
    ├── foo-bar.spec.ts
    ├── foo-bar.test.ts
    ├── foo-bar.e2e-spec.ts
    └── foo-bar.e2e-test.ts
    index.ts
    └── index.d.ts
    ```

---
- **React**

    Expected nesting structure for a React (TSX) project:
    ```bash
    Dashboard.tsx
    ├── Dashboard.spec.tsx
    ├── Dashboard.test.tsx
    ├── Dashboard.e2e-spec.tsx
    ├── Dashboard.e2e-test.tsx
    └── Dashboard.stories.tsx
    dashboard.page.tsx
    ├── dashboard.page.spec.tsx
    ├── dashboard.page.test.tsx
    ├── dashboard.page.e2e-spec.tsx
    ├── dashboard.page.e2e-test.tsx
    └── dashboard.page.stories.tsx
    ```

---
- **NestJS**

    Expected nesting structure for a NestJS project:
    ```bash
    foo.controller.ts
    ├── foo.controller.spec.ts
    └── foo.controller.e2e-spec.ts
    foo.service.ts
    ├── foo.service.spec.ts
    └── foo.service.e2e-spec.ts
    foo.repository.ts
    ├── foo.repository.spec.ts
    └── foo.repository.e2e-spec.ts
    foo.use-case.ts
    ├── foo.use-case.spec.ts
    └── foo.use-case.e2e-spec.ts
    foo.module.ts
    foo.entity.ts
    foo.interface.ts
    ```


## Rules

- **Neo-tree (Nixvim)**

    Rules for grouping related files under their primary source file.
    ```nix
    plugins.neo-tree.settings.nesting_rules = {
        "ts-declarations" = {
            priority = 100;
            pattern = "(.+)%.ts$";
            files = [
                "%1.d.ts"
                "%1.type.ts"
                "%1.interface.ts"
            ];
        };
        "ts-base-test" = {
            priority = 100;
            pattern = "(.+)%.ts$";
            files = [
                "%1.spec.ts"
                "%1.test.ts"
                "%1.e2e-spec.ts"
                "%1.e2e-test.ts"
            ];
        };
        "ts-react-test" = {
            priority = 100;
            pattern = "(.+)%.tsx$";
            files = [
                "%1.spec.tsx"
                "%1.test.tsx"
                "%1.e2e-spec.tsx"
                "%1.e2e-test.tsx"
                "%1.stories.tsx"
            ];
        };
    };
    ```
