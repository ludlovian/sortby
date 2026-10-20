# sortBy
Creates sorting functions

## API

Single default export

### sortBy
```
import sortBy from '@ludlovian/sortby'

arr.sort(sortBy(selector, desc?))
```

Creates a sorting function based on the selected value.
The supplied `selector` can be:

- an attribute name,
- a selector function,
- a 2-parameter comparison function

If it is a name or selector function which produces class instances,
then the comparison will be made using a static `.compare` function
if one exists (e.g. Temporal.Instant.compare).

Otherwise, simple `<` and `>` tests are applied.

If you want to reverse the sort order, set `desc` to a truthy value.

### thenBy

Every `sortBy` (or `thenBy`) function has a `thenBy` to create multiple levels of sorting

```
arr.sort(sortBy('region').thenBy((item => item.sales.volume), true))
```
