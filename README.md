# R_Projects
This is a place to hold R coding projects

library(dplyr)
library(ggplot2)
library(dslabs)
data(gapminder)
gapminder %>% filter(continent == "Africa", year == 1970 | 2010, !is.na(gdp)) %>% 
    mutate(dollars_per_day = gdp/population/365) %>% ggplot(aes(dollars_per_day, y = ..count..))  + scale_x_continuous(trans = "log2") + geom_density ()
+ facet_grid (. ~ year)

