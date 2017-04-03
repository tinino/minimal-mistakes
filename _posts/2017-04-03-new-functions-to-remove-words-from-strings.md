---
title: "New functions to remove words from strings"
category:
- "R"
- "tinotools"
---

After creating and collecting functions regarding string manipulation in the script, I today decided to finally include them in my package. Since I'm right now trying to match more or less similar
names in our database to avoid double entries, I came up with some useful functions, especially if you use them in combinations with the [tidyverse-packages](http://tidyverse.org/).
Because this script became quite messy, I picked those functions that might be useful again sometimes and source them from [my package](https://github.com/tinino/tinotools) from now on. Especially
the `str_remove`*-functions are nice if you for example have to deal with companies and---for some reason---they sometimes have different entities or abbreviations, making it hard to match or even
find possible candidates using `agrep()` or `stringdist::stringsim()`. Using `string_remove_not_left(string = "Some Company Limited Co", remove_words = c("Some", "Limited", "Co"))` 
becomes `Some Company` (and not `Company`, because of *not* using `string_remove_only_left()` or `string_remove()`) and hence makes it more likely to find proper matches using for example
`stringdist::stringsim()` for typo-detection.
