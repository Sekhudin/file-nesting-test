## Expected Result

- **Rust**

    Expected nesting structure for a Rust-based project:    
    ```bash
    foo.rs
    └── foo_test.rs
    ```


## Rules

- **Neo-tree (Nixvim)**

Rules for grouping related files under their primary source file.
```nix
plugins.neo-tree.settings.nesting_rules = {
    "rust-base-test" = {
        priority = 100;
        pattern = "(.+)%.rs$";
        files = [
            "%1_test.rs"
        ];
    };
};
```
