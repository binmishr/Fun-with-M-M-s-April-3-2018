# Fun-with-M-M-s-April-3-2018

The details of the codeset and plots are included in the attached Microsoft Word Document (.docx) file in this repository. 
You need to view the file in "Read Mode" to see the contents properly after downloading the same.

A Brief Introduction - Scimple Package
=========================================

```{r badges, results='asis', echo=FALSE, cache=FALSE}
hrbrpkghelpr::stinking_badges()
```

```{r description, results='asis', echo=FALSE, cache=FALSE}
hrbrpkghelpr::yank_title_and_description()
```

## What's Inside The Tin

The following functions are implemented:

```{r ingredients, results='asis', echo=FALSE, cache=FALSE}
hrbrpkghelpr::describe_ingredients()
```

There's also a handy named vector `scimple_short_to_long` which you can use to expand
shorthand method names (e.g. "sg") to long (e.g. "Sison & Glaz").

### Installation

Package installation:

```{r install-ex, results='asis', echo=FALSE, cache=FALSE}
hrbrpkghelpr::install_block()
```

### Usage

```{r u01, fig.width=10, fig.height=5.5}
library(scimple)
library(hrbrthemes)
library(tidyverse)

y <- c(44, 55, 43, 32, 67, 78)
z <- 0.05

scimple_ci(y, z) %>% 
  mutate(method=scimple_short_to_long[method]) -> cis

print(cis)

ggplot(cis) +
  geom_segment(aes(x=lower_limit, xend=upper_limit, y=method, yend=method, color=method)) +
  scale_color_ipsum(name=NULL) +
  facet_wrap(~inpmat, scales="free_x") +
  labs(x=NULL, y=NULL, 
       title="Multipe simultaneous confidence intervals",
       subtitle="Note free X scale") +
  theme_ipsum_rc(grid="X", base_size=11) +
  theme(legend.position="bottom")
```

## scimple Metrics

```{r cloc, echo=FALSE}
cloc::cloc_pkg_md()
```
