# [OneStepabcd](https://github.com/kanghuadu/OneStepabcd)
[![DuLab](https://img.shields.io/badge/DuLab-github-blue?logo=github)](https://github.com/kanghuadu)

# One Step ANOVA and Plot
This function performs one-way ANOVA and plots the results with custom themes.

## Install 
```R
# install.packages("devtools")
devtools::install_github("kanghuadu/OneStepabcd")
```

## Usage
Make a single plot
```R
oneStep_abcd_analysis(
  data_matrix,
  y_lab = "",
  x_lab = "",
  theme_params = theme_classic(),
  title = "",
  custom_theme = theme(text = element_text(color = "black", size = 10), axis.text.x =
    element_text(color = "black", size = 12), axis.text.y = element_text(color = "black",
    size = 12), axis.ticks = element_line(color = "black"), strip.text =
    element_text(color = "black", size = 10), axis.title = element_text(color = "black",
    size = 12), legend.position = "none", strip.background = element_blank()),
  fill_color = scale_fill_manual(values = c("#1f78b4", "#ff7f00", "#4daf4a", "#fb8072",
    "#8da0cb", "#bf5b17", "#b2df8a", "#c8c9c9", "#7570b3"))
)
```

## Optional
- data_matrix: Data frame containing the data to be analyzed.
- y_lab: Label for the y-axis.
- x_lab: Label for the x-axis.
- theme_params: ggplot2 theme parameters.
- title: Title of the plot.
- custom_theme: Custom ggplot2 theme settings.
- fill_color: Color scheme for the plot.

## Example
```R
data(example_data)
oneStep_abcd_analysis(example_data, y_lab = "Weight of a thousand seeds", x_lab = NULL,
                      fill_color = scale_fill_manual(values = c("red","green","#c8c9c9", "#7570b3")),
                      theme_params = theme_bw())
```
