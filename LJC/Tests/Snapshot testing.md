To allow incremental development and testing, we want to be able to test each stage (e.g. lexer, parser, etc.) individually.

This is accomplished using "snapshot tests" (aka "golden" tests).
The lexer is invoked on a collection of input programs, and the returned token sequence is saved as a "snapshot" for future reference.

To get the snapshot functionality we use [insta](https://insta.rs/docs/)


```rust
use ljc::lexer::lexer::Tokens;  
use std::fs;  
  
fn lex_to_string(input: &str) -> String {  
let mut tokens = Tokens::new(input.to_string());  
let mut out = String::new();  
  
while let Ok(Some(token)) = tokens.next() {  
out.push_str(&format!("{:?}\n", token));  
}  
  
out  
}  
  
#[test]  
fn snapshot_lexer_test1() {  
let input = fs::read_to_string("tests/snapshot/inputs/test1.java").unwrap();  
let output = lex_to_string(&input);  
  
insta::assert_snapshot!(output);  
}
```