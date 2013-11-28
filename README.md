event0
======

Javascript Event-Emitter-Receiver implementation with a twist 


```javascript 
/**
SUMMARY:
    We deal with events, emitters, receivers and listeners.
    Both emitter and receiver are objects. When certain conditions happen
    in a emitter object, this emits an event, which is a message sent through
    a listener function. 
    The event has:
        * event_type. Listeners register or 'subcribe' for a type of event;
        * event_data (the message itself, it can be a reference to an object).
    When an event of event_type is emitted, all the functions previously 
    registered for that event_type are called sequentially, with event_data
    as an argument. A reference to the event_emitter is also passed to the 
    listener function (wether as an additional argument or injected into the 
    function as the 'this' variable).
    The listener can be bounded to the emitter object (as usual in other framework
    as jquery and nodejs) or to the receiver object with extended methods 
    (addListenerX() and its equivalent onX()).
    
    **Case 1** (Like in jquery and nodejs. Listener bounded to emitter).
    EMITTER-(calls)->listener()                                    RECEIVER
    The listener is bounded to the emitter, as if it were a method.
    The receiver would be called indirectly if it is an object, but often 
    it is a closure context.
    
    **Case 2** (extended. Listener bounded to receiver).
    EMITTER-(calls)----------------------------------->listener()->RECEIVER
    The listener is now a method of the RECEIVER.
    This case makes it easier to call a listener when it is a method 
    of other object.
 */
```
