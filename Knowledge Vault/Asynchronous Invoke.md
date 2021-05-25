- When invoke a function asynchronously, we send the event to [[Event Queue]]. Later, Lambda read events from the [[Event Queue]].
- [[Error Handling in Asynchronous]] is to retry on error.
- If the function doesn't have enough [[Lambda Concurrency]], the additional requests will be returned to [[Event Queue]]. And gonna be run again after interval for up to 6 hours. The interval increases exponentially from 1 second after the first attemp to a maximum of 5 minutes.

Backlink: [[Lambda events]]