## Expected Result

- **Java**

    Expected nesting structure for a Java-based project:    
    ```bash
    Foo.java
    ├── FooIT.java
    └── FooTest.java
    FooBar.java
    ├── FooBarIT.java
    └── FooBarTest.java
    ```


## Rules

- **Neo-tree (Nixvim)**

Rules for grouping related files under their primary source file.
```nix
plugins.neo-tree.settings.nesting_rules = {
    "java-base-test" = {
        priority = 100;
        pattern = "(.+)%.java$";
        files = [
            "%1IT.java"
            "%1Test.java"
        ];
    };
};
```
