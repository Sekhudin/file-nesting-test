## Expected Result

- **Go**

    Expected nesting structure for a Go-based project:    
    ```bash
    foo.go
    └── foo_mock.go
    └── foo_test.go
    └── foo_benchmark_test.go
    └── foo_fuzz_test.go
    ```


## Rules

- **Neo-tree (Nixvim)**

    Rules for grouping related files under their primary source file.
    ```nix
    plugins.neo-tree.settings.nesting_rules = {
        "go-base-test" = {
            priority = 100;
            pattern = "(.+)%.go$";
            files = [
                "%1_test.go"
            ];
        };
        "go-extended-test" = {
            priority = 100;
            pattern = "(.+)%.go$";
            files = [
                "%1_benchmark_test.go"
                "%1_fuzz_test.go"
            ];
        };
        "go-base-mock" = {
            priority = 100;
            pattern = "(.+)%.go$";
            files = [
                "%1_mock.go"
            ];
        };
    };
    ```
