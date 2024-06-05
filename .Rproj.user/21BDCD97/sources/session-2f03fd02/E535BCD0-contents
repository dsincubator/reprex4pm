### Mechanics

Select code then: Addins > Reprex selection

```r
1 + 1
```

Same

```r
reprex::reprex(1 + 1)
```

Same

```r
reprex::reprex({
 1 + 1
})
```

Prefer data that is small and built-in

```r
data <- mtcars[1:3, 1:2]
data
```

State what you expected and what you got instead

> "Expected "Datsun 710" but got an error"

```r
filter(data, cyl < 6)
```

Remember to use `library()`. Prefer to create data with code.

```r
library(dplyr)

# data <- mtcars[1:3, 1:2]
# datapasta::tribble_paste(data)
data <- tibble::tribble(
  ~mpg, ~cyl,
    21,    6,
    21,    6,
  22.8,    4
  )

# Oops! Now it works!
filter(data, cyl < 6)
```

If you must use local data, use `wd = "."`
And/or share link to your posit.cloud project including data

```r
reprex::reprex(wd = ".", {
  # Prefer .tsv to avoid issues from different decimal points
  data <- readr::read_tsv("data/data.tsv")
  filter(data, cyl < 6)
})
```

Links:

* This is standard, e.g.: https://github.com/tidyverse/dplyr/issues/new
* See https://reprex.tidyverse.org/articles/reprex-dos-and-donts.html
