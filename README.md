## Issue which I found.

### Default scenario to call multiple handlers for same event on same element:

Each event handler is independent. Errors in any handler should not affect other handlers. So is I assign 3 handler for click on button, then no matter how many errors will be thrown - each function will be called. In my example I added 3 handler to first button and I throw error in first handler - in the console we can see 3 logs + message about error, so everything woks as expected.

### Behavior with ZoneJS:

I also added 3 more similar click event handlers to the second button, but I did that after loading the script with zonejs, so these event handlers are in root zone. After click on the button you will see only log from the first handler and message about error. Other two logs are absent -  other handlers are not called.

### Page to reproduce:

[Static page from that repo](https://matrosskin.github.io/zonejs-multiple-event-listeners/public/)
