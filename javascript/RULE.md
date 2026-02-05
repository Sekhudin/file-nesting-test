## Expected Result

- **JavaScript**

    Expected nesting structure for a JavaScript-based project:    
    ```bash
    foo.js
    ├── foo.d.ts
    ├── foo.map.js
    ├── foo.spec.js
    ├── foo.test.js
    ├── foo.e2e-spec.js
    └── foo.e2e-test.js
    foo-bar.js
    ├── foo-bar.d.ts
    ├── foo-bar.js.map
    ├── foo-bar.spec.js
    ├── foo-bar.test.js
    ├── foo-bar.e2e-spec.js
    └── foo-bar.e2e-test.js
    index.js
    ├── index.d.ts
    └── index.js.map
    ```

---
- **React**

    Expected nesting structure for a React (JSX) project:
    ```bash
    Dashboard.jsx
    ├── Dashboard.spec.jsx
    ├── Dashboard.test.jsx
    ├── Dashboard.e2e-spec.jsx
    ├── Dashboard.e2e-test.jsx
    └── Dashboard.stories.jsx
    dashboard.page.jsx
    ├── dashboard.page.spec.jsx
    ├── dashboard.page.test.jsx
    ├── dashboard.page.e2e-spec.jsx
    ├── dashboard.page.e2e-test.jsx
    └── dashboard.page.stories.jsx
    ```

---
- **NestJS**

    Expected nesting structure for a NestJS project:
    ```bash
    foo.controller.js
    ├── foo.controller.spec.js
    └── foo.controller.e2e-spec.js
    foo.service.js
    ├── foo.service.spec.js
    └── foo.service.e2e-spec.js
    foo.repository.js
    ├── foo.repository.spec.js
    └── foo.repository.e2e-spec.js
    foo.use-case.js
    ├── foo.use-case.spec.js
    └── foo.use-case.e2e-spec.js
    foo.module.js
    foo.entity.js
    ```


## Rules

- **Neo-tree (Nixvim)**

    Rules for grouping related files under their primary source file.
    ```nix
    plugins.neo-tree.settings.nesting_rules = {
        "js-declarations" = {
            priority = 100;
            pattern = "(.+)%.js$";
            files = [
                "%1.d.ts"
                "%1.js.map"
            ];
        };
        "js-base-test" = {
            priority = 100;
            pattern = "(.+)%.js$";
            files = [
                "%1.spec.js"
                "%1.test.js"
                "%1.e2e-spec.js"
                "%1.e2e-test.js"
            ];
        };
        "js-react-test" = {
            priority = 100;
            pattern = "(.+)%.jsx$";
            files = [
                "%1.spec.jsx"
                "%1.test.jsx"
                "%1.e2e-spec.jsx"
                "%1.e2e-test.jsx"
                "%1.stories.jsx"
            ];
        };
    };
    ```
