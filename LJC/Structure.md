```
 .
├── Cargo.toml
├── src/
│   ├── lib.rs
│   ├── main.rs
│   │
│   ├── lexer/  
│   │   ├── mod.rs  
│   │   ├── token.rs  
│   │   └── lexer.rs  
│   |
│   ├── parser/  
│   │   ├── mod.rs  
│   │   └── parser.rs 
│   │   
│   ├── ast/
│   │   ├── compilation_unit.rs
│   │   ├── declarations.rs
│   │   ├── expressions.rs
│   │   ├── identifiers.rs
│   │   ├── mod.rs
│   │   ├── modifiers.rs
│   │   ├── patterns.rs
│   │   ├── printer.rs
│   │   ├── statements.rs
│   │   ├── switch.rs
│   │   └── types.rs
│   |
│   ├── semantic/  
│   │   ├── mod.rs  
│   │   ├── symbol_table.rs  
│   │   └── type_check.rs  
│   | 
│   ├── ir/  
│   │   ├── mod.rs  
│   │   └── ir.rs  
│   |   
│   ├── codegen/  
│   │   ├── mod.rs  
│   │   └── llvm.rs  
│   | 
│   └── diagnostics/  
│       ├── mod.rs  
│       └── error.rs  
│
└── tests/
    ├── snapshot/
    |   ├── snapshot_test.rs
    │   ├── lexer/
    │   ├── parser/
    │   └── inputs/
    │       └── *.java
    │
    ├── e2e/
    │   ├── api.rs
    │   ├── cli.rs
    │   └── programs/
    │       ├── valid/
    │       └── invalid/
    │
    └── fuzz/
        └── fuzz_targets/
            └── lexer.rs
```