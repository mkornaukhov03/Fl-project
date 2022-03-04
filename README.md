# Fl-project

[Abstract language description (In Russian) ](https://github.com/kajigor/fl-2021-hse-win/blob/proj/lang/L.md)  
[Specific language description (In Russian)](ConcreteSyntax.md)  
[Tests](tests/error_handling/)  
[Examples](tests/valid)
___
## Features overview
* Single function(main)
* One scope for entire program
* Single line comments
* 3 types: `Int(32 bit), Bool, String`
* Literals: `0b10101, 42, 'str', "another string", True`
* Operators:
   * Declaration and assignment
   * `skip`
   * `if` with optional `else`
   * `while`
   * `print` (prints `String` or `Int`)
* Expression
   * `'+' \ '-' \ '*' \ '/'` - for operands of `Int` type
   * `'<', '>', '<=', '>='`  - for operands of `Int` type
   * `'==', '!='`            - for operands of all types
   * `'!', '&&', '||'`       - for operands of `'Bool'` type
___
## Examples
* GCD
    ```Go
    main() {
        // gcd(30, 24)
        Int x = 30;
        Int y = 24;
        while (x != 0) {
            if (y < x) {
                Int tmp = y;
                y = x;
                x = tmp;
            }
            y = y - x; 
        }
        print y;
    }
    ```
* Finding sqrt
    ```Go
    main() {
        // finding sqrt(144) 
        Int val = 144;
        Int x = 0;
        while (x * x < val) {
            x = x + 1;
        }
        if (x * x == val) {
            print "Precise square root of val = ";
            print x;
        }
        else {
            print "Sqrt is not integer!";
        }
    }
    ```
___
## Build
### Prerequisites
* `Flex`
* `Bison`
* `LLVM`
* `Clang`
### How to compile
`l_to_exec.sh *source_file* *output_binary_file*`