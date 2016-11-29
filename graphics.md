Indicators
================

### Rent vs population

``` r
library(ggplot2)

data <- read.csv("data/renta_cantabria.csv")
pop <- read.csv("data/pop_cantabria.csv")

# Merge the datasets
merged <- merge(x = data, y = pop, by = "location_id", all.x = TRUE)

# Scatterplot
ggplot(merged, aes(log(value.y), value.x, color = value.x)) +
  geom_smooth(method='lm', color="black", se = FALSE, size = 0.3) +
  geom_point(size = 5, color="darkred", alpha = 0.35)
```

![](graphics_files/figure-markdown_github/unnamed-chunk-1-1.png)
