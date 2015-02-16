# CancelBlocks

Set of functions for dispatching blocks after a delay, with the ability to cancel them. Written in Swift.
Use dispatch_block_t instead of native dispatch_after and save the executing block with type dispatch_cancelable_block_t, afterwards
you could safely use it to cancel executing block by using dispatch_cancel_block_t.

Example:
var block:dispatch_cancelable_block_t? =  dispatch_block_t(1, { () -> Void in
    // Your code 
})
dispatch_cancel_block_t(block)
