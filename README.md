# CancelBlocks

Set of functions for dispatching blocks after a delay, with the ability to cancel them. Written in Swift.

Use `dispatch_block_t` instead of native `dispatch_after` and save the executing block with type `dispatch_cancelable_block_t`, afterwards you may safely use it to cancel executing the block by using `dispatch_cancel_block_t`.

`dispatch_cancelable_block_t` wraps your block in a block of type `(Bool) -> Void` which handles cancellation.

Usage example:

```
var block: dispatch_cancelable_block_t? = dispatch_block_t(1, {
    // Your code 
})
dispatch_cancel_block_t(block)
```
