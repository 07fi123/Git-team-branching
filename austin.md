Blee

```zig
const std = @import("std");

pub fn main() !void {
    std.debug.print("Hello, World!\n", .{});
}
pub fn addTwoNumbers(a: i32, b: i32) !i32 {
    return a + b;
}

// Test the function
const test_result = try addTwoNumbers(5, 7);
std.debug.print("The sum of 5 and 7 is {d}\n", .{test_result});

```
