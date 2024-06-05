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

* Prefer data that is small and built-in.
* Show the data so the reader can run it in their head.
* State what you expected and what you got instead.

```r
data <- mtcars[1:3, 1:2]
data

# > Expected "Datsun 710" but got an error
filter(data, cyl < 6)
```

* Remember to use `library()`. Prefer to create data with code.
* Prefer to create the data with code.

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

# Yay! Now it works!
filter(data, cyl < 6)
```

* If you must use local data, then you need `wd = "."`
* You can share a link to your posit.cloud project including data.
* Prefer .tsv over .csv to avoid issues from different decimal points.

```r
reprex::reprex(wd = ".", {
  data <- readr::read_tsv("data/data.tsv")
  filter(data, cyl < 6)
})
```

Links:

* Asking for a reprex is standard, e.g. see the [issue template of dplyr](https://github.com/tidyverse/dplyr/issues/new).
* Learn more at [repres do's and dont's](https://reprex.tidyverse.org/articles/reprex-dos-and-donts.html)
