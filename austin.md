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

pub fn deepCopyIntPtr(ptr: ?*i32) !?*i32 {
    const new_ptr = std.heap.calloc(1, @sizeOf(*i32)) catch unreachable;
    std.mem.copy(i32, @ptrCast(*[1] i32, new_ptr)[0..], ptr.*);
    return new_ptr;
}

// Test the function
const original_value = 42;
var ptr: ?*i32 = try std.heap.calloc(1, @sizeOf(i32)) catch unreachable;
defer std.heap.free(ptr);
ptr.* = original_value;

const copied_ptr = try deepCopyIntPtr(ptr);
std.debug.print("Original value: {d}\n", .{ptr.*});
std.debug.print("Copied value: {d}\n", .{copied_ptr.*});


```
