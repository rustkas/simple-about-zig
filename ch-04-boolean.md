const std = @import("std");

pub fn main() void {
    const false_variable = false;
    const true_variable = true;

    std.debug.print("{} {}\n", .{! true_variable, ! false_variable});
    std.debug.print("{} {} {} {}\n", .{
        false_variable or false_variable,
        false_variable or true_variable,
        true_variable or false_variable,
        true_variable or true_variable
    });

    std.debug.print("{} {} {} {}\n", .{
        false_variable and false_variable,
        false_variable and true_variable,
        true_variable and false_variable,
        true_variable and true_variable
    });
}
```

Порядок выполнения логических операций: `not`, `and`, `or`. Он может быть изменён с помощью круглых скобок.

```zig
const std = @import("std");

pub fn main() void {
    const false_variable = false;
    const true_variable = true;

    std.debug.print("{}\n", .{true_variable or false_variable and !true_variable});
    std.debug.print("{}\n", .{(true_variable or false_variable) and !true_variable});
}
```

## Домашнее задание

Попробуйте создать цепочки логических вычислений с данными различных типов в Zig, используя логические и сравнительные операторы. Изучите, как работают операторы в Zig и как можно управлять порядком операций с помощью скобок.
