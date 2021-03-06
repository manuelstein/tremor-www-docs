# The `win` namespace

The `win` module contains functions for aggregating over the current active window in a window of events. The functions can also be used in tilt frames where events emitting from a window are chained across multiple window frames in sequence.

## Functions

### aggr::win::first() -> event

Capture and return the first event that hits a window upon/after opening.

```trickle
aggr::win::first() # first event in a window
```

### aggr::win::last() -> event

Capture and return the last event that hits a window upon/after opening.

```trickle
aggr::win::last()
```

### aggr::win::collect_flattened() -> [event]

Captures all events in a window into an array of events.

In the case of tilt frames,  flattens out any tilt frame sub-arrays

```trickle
aggr::win::collect_flattened()
```

### aggr::win::collect_nested() -> [[event]]|[event]

Captures all events in a window into an array of events.

In the case of tilt frames, each frame is preserved as a nested array of arrays. For a tilt frame of 3 windows, the inner-most leaf array contains events, and higher levels are arrays of arrays.

```trickle
aggr::win::collect_nested()
```