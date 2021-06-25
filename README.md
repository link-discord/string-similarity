# string-similarity
A deno port of the string similarity npm package.
# Usage
```js
import * as stringSimilarity from 'https://deno.land/x/string_similarity/mod.ts'

stringSimilarity.compareTwoStrings("healed", "sealed");
// → 0.8

stringSimilarity.compareTwoStrings(
  "Olive-green table for sale, in extremely good condition.",
  "For sale: table in very good  condition, olive green in colour."
);
// → 0.6060606060606061

stringSimilarity.compareTwoStrings(
  "Olive-green table for sale, in extremely good condition.",
  "For sale: green Subaru Impreza, 210,000 miles"
);
// → 0.2558139534883721

stringSimilarity.compareTwoStrings(
  "Olive-green table for sale, in extremely good condition.",
  "Wanted: mountain bike with at least 21 gears."
);
// → 0.1411764705882353

stringSimilarity.findBestMatch('Olive-green table for sale, in extremely good condition.', [
  'For sale: green Subaru Impreza, 210,000 miles',
  'For sale: table in very good condition, olive green in colour.',
  'Wanted: mountain bike with at least 21 gears.'
]);
// →
{ ratings:
   [ { target: 'For sale: green Subaru Impreza, 210,000 miles',
       rating: 0.2558139534883721 },
     { target: 'For sale: table in very good condition, olive green in colour.',
       rating: 0.6060606060606061 },
     { target: 'Wanted: mountain bike with at least 21 gears.',
       rating: 0.1411764705882353 } ],
  bestMatch:
   { target: 'For sale: table in very good condition, olive green in colour.',
     rating: 0.6060606060606061 },
  bestMatchIndex: 1
}
```
