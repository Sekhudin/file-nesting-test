## Expected Result

- **Python**

    Expected nesting structure for a Python-based project:    
    ```bash
    foo.py
    └── foo_test.py
    bar_foo.py
    └── bar_foo_test.py
    foobar.py
    └── test_foobar.py
    foo_bar.py
    └── test_foo_bar.py
    ```


## Rules

- **Neo-tree (Nixvim)**

Rules for grouping related files under their primary source file.
```nix
plugins.neo-tree.settings.nesting_rules = {
    "python-base-test" = {
        priority = 100;
        pattern = "(.+)%.py$";
        files = [
            "test_%1.py"
            "%1_test.py"
        ];
    };
};
```
