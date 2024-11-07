
## Арифметические вычисления

### Сложение и вычитание целых чисел

Рассмотрим сложение двух чисел:

```zig
const std = @import("std");

pub fn main() void {
    // Сложение и вычитание целых чисел
    std.debug.print("Сумма чисел равна {d}\n", .{2 + 2});
    std.debug.print("Разность чисел равна {d}\n", .{2 - 2});
}
```
[Zig Playground](https://codapi.org/embed/?sandbox=zig&code=data%3A%3Bbase64%2CjY49DoJwDMV3TvHCBFEhYTUmHsRFRA0Df4iiCyERjDroIeQGhAQl8eMM7Y2sH4ODg%2B30Xvt%2B7ShU8xjz2EMPfT%2BIwlls6CJ1s6tp0cLFRCEY%2BsowsQx9D4kGKdsGFXShO52ophs1VIMaUMV73lHDOZUfl7eycBF7g9cke8oXQ45Y3thdTK1o5iu5SgWv6Spdfq2CV8KqhFYi8dKB0tuwEgctOKm8%2BBt0lMhZInfOOOfDH7jOG5c%2BAA%3D%3D)
Во время работы программы происходит сложение и вычитание двух чисел, результаты вставляются в текстовый шаблон и выводятся на консоль.

### Умножение и деление целых чисел

Более сложные вычисления — умножение и деление — также выполняются без сложностей:

```zig
const std = @import("std");

pub fn main() void {
    // Умножение и деление целых чисел
    std.debug.print("Произведение чисел равно {d}\n", .{2 * 2});
    std.debug.print("Частное чисел равно {d}\n", .{2 / 2});
}
```

Попробуйте закомментировать деление на `0` — компилятор Zig проверит код и не позволит программе скомпилироваться с этой ошибкой. Это помогает избежать неожиданных ошибок, но будьте внимательны, так как при работе с переменными вы можете случайно создать ситуацию деления на ноль.

### Другие математические операции над целыми числами

Язык Zig поддерживает основные математические операции над числами: сложение, вычитание, умножение и деление. Также доступно вычисление остатка от деления `%`. Порядок выполнения операций можно изменять с помощью круглых скобок.

Рассмотрим пример работы этих математических операций в различных комбинациях:

```zig
const std = @import("std");

pub fn main() void {
    std.debug.print("{d}\n", .{2 + 2 - 2 * 2 / 2 % 2});
    std.debug.print("{d}\n", .{(2 + 2) - 2 * 2 / 2 % 2});
    std.debug.print("{d}\n", .{2 + (2 - 2) - 2 / 2 % 2});
    std.debug.print("{d}\n", .{2 + 2 - 2 * (2 / 2) % 2});

    // эта строка вызывает деление на 0 и будет ошибкой компиляции
    // std.debug.print("{d}\n", .{2 + 2 - 2 * 2 / (2 % 2)}); // Ошибка компиляции
}

```

Компилятор Zig обнаруживает попытку деления на ноль и не позволяет скомпилировать код, предотвращая возникновение ошибок во время выполнения программы.


```markdown
### Арифметические операции над дробными числами

Рассмотрим использование математических операций при работе с дробными числами:

```zig
const std = @import("std");

pub fn main() void {
    std.debug.print("Сумма:\n", .{});
    std.debug.print("{:.}\n", .{0.1 + 0.1});
    std.debug.print("{:.}\n", .{0.1 + 0.2});
    std.debug.print("{:.}\n", .{0.1 + 0.3});
    std.debug.print("{:.}\n", .{0.1 + 0.4});
    std.debug.print("{:.}\n", .{0.1 + 0.5});
    std.debug.print("{:.}\n", .{0.1 + 0.6});
    std.debug.print("{:.}\n", .{0.1 + 0.7});
    std.debug.print("{:.}\n", .{0.1 + 0.8});
    std.debug.print("{:.}\n", .{0.1 + 0.9});
    
    std.debug.print("Разность:\n", .{});
    std.debug.print("{:.}\n", .{0.1 - 0.1});
    std.debug.print("{:.}\n", .{0.1 - 0.2});
    std.debug.print("{:.}\n", .{0.1 - 0.3});
    std.debug.print("{:.}\n", .{0.1 - 0.4});
    std.debug.print("{:.}\n", .{0.1 - 0.5});
    std.debug.print("{:.}\n", .{0.1 - 0.6});
    std.debug.print("{:.}\n", .{0.1 - 0.7});
    std.debug.print("{:.}\n", .{0.1 - 0.8});
    std.debug.print("{:.}\n", .{0.1 - 0.9});

    std.debug.print("Умножение:\n", .{});
    std.debug.print("{:.}\n", .{0.1 * 0.1});
    std.debug.print("{:.}\n", .{0.1 * 0.2});
    std.debug.print("{:.}\n", .{0.1 * 0.3});
    std.debug.print("{:.}\n", .{0.1 * 0.4});
    std.debug.print("{:.}\n", .{0.1 * 0.5});
    std.debug.print("{:.}\n", .{0.1 * 0.6});
    std.debug.print("{:.}\n", .{0.1 * 0.7});
    std.debug.print("{:.}\n", .{0.1 * 0.8});
    std.debug.print("{:.}\n", .{0.1 * 0.9});

    std.debug.print("Деление:\n", .{});
    std.debug.print("{:.}\n", .{0.1 / 0.1});
    std.debug.print("{:.}\n", .{0.1 / 0.2});
    std.debug.print("{:.}\n", .{0.1 / 0.3});
    std.debug.print("{:.}\n", .{0.1 / 0.4});
    std.debug.print("{:.}\n", .{0.1 / 0.5});
    std.debug.print("{:.}\n", .{0.1 / 0.6});
    std.debug.print("{:.}\n", .{0.1 / 0.7});
    std.debug.print("{:.}\n", .{0.1 / 0.8});
    std.debug.print("{:.}\n", .{0.1 / 0.9});

    std.debug.print("Остаток от деления:\n", .{});
    std.debug.print("{:.}\n", .{0.1 % 0.1});
    std.debug.print("{:.}\n", .{0.1 % 0.2});
    std.debug.print("{:.}\n", .{0.1 % 0.3});
    std.debug.print("{:.}\n", .{0.1 % 0.4});
    std.debug.print("{:.}\n", .{0.1 % 0.5});
    std.debug.print("{:.}\n", .{0.1 % 0.6});
    std.debug.print("{:.}\n", .{0.1 % 0.7});
    std.debug.print("{:.}\n", .{0.1 % 0.8});
    std.debug.print("{:.}\n", .{0.1 % 0.9});
}
```

В языке Zig поддерживается работа с дробными числами, включая сложение, вычитание, умножение, деление и вычисление остатка.
