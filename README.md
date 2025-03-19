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
- **data_matrix**: Data frame containing the data to be analyzed.
- **y_lab**: Label for the y-axis.
- **x_lab**: Label for the x-axis.
- **theme_params**: ggplot2 theme parameters.
- **title**: Title of the plot.
- **custom_theme**: Custom ggplot2 theme settings.
- **fill_color**: Color scheme for the plot.

## Example
```R
data(example_data)
```
```R
   sample repeat01 repeat02 repeat03
1      CK 4.719762 3.389983 5.093666
2      CK 4.884911 2.958315 4.766305
3      CK 5.779354 3.126659 3.882150
4      CK 5.035254 2.985727 3.486790
5      CK 5.064644 2.978565 3.644797
6      CK 5.857532 3.684301 4.128442
7    80-1 5.230458 2.887115 3.876654
8    80-1 4.367469 3.758235 3.826229
9    80-1 4.656574 2.225624 3.524191
10   80-1 4.777169 3.292307 3.977486
11   80-1 5.612041 3.061927 3.607548
12   80-1 5.179907 3.107971 3.166029
13    4-7 5.200386 3.189820 3.809887
14    4-7 5.055341 2.748838 4.459498
15    4-7 4.722079 2.833396 3.712327
16    4-7 5.893457 2.490712 4.303982
17    4-7 5.248925 2.464104 3.191059
18    4-7 4.016691 3.151764 3.972219
19   4-14 5.350678 3.224105 4.259704
20   4-14 4.763604 3.026502 4.150577
21   4-14 4.466088 3.461134 4.052838
22   4-14 4.891013 4.025042 3.679647
23   4-14 4.486998 2.754484 3.575148
24   4-14 4.635554 1.845416 3.487936
25   4-60 4.687480 3.502869 4.058823
26   4-60 4.156653 2.645400 3.526263
27   4-60 5.418894 2.655996 3.754721
28   4-60 5.076687 3.512786 3.871954
29   4-60 4.430932 2.857613 4.921931
30   4-60 5.626907 2.389641 3.674025
31   20-7 5.213232 3.090652 4.117693
32   20-7 4.852464 2.930554 4.038980
33   20-7 5.447563 3.002882 3.519072
34   20-7 5.439067 3.192640 3.964346
35   20-7 5.410791 2.814670 4.722275
36   20-7 5.344320 3.322188 4.225752
37  20-14 5.276959 2.889757 4.020616
38  20-14 4.969044 3.165891 3.788752
39  20-14 4.847019 3.548420 2.973376
40  20-14 4.809764 3.217591 4.565669
41  20-14 4.652647 2.837034 3.269680
42  20-14 4.896041 3.574404 4.369974
43  20-60 4.367302 3.496752 4.954552
44  20-60 6.084478 3.274198 3.278053
45  20-60 5.603981 3.119366 4.350892
46  20-60 4.438446 2.686047 3.868901
47  20-60 4.798558 3.680326 3.213928
48  20-60 4.766672 2.699870 3.242666
```
```R
oneStep_abcd_analysis(example_data, y_lab = "Weight of a thousand seeds", x_lab = NULL,
                      #fill_color = scale_fill_manual(values = c("red","green","#c8c9c9", "#7570b3")),
                      theme_params = theme_bw())
```
![](https://github.com/kanghuadu/OneStepabcd/blob/main/data/Rplot.jpeg)

```R
          Df Sum Sq Mean Sq F value Pr(>F)
sample        7   1.66  0.2373   0.268  0.965
Residuals   136 120.54  0.8863               
$statistics
    MSerror  Df     Mean       CV       MSD
  0.8863305 136 3.994579 23.56822 0.9661442

$parameters
   test name.t ntr StudentizedRange alpha
  Tukey sample   8         4.353919  0.05

$means
         value       std  r        se      Min
20-14 3.981813 0.8236589 18 0.2219022 2.837034
20-60 3.995833 0.9794606 18 0.2219022 2.686047
20-7  4.147175 0.9723936 18 0.2219022 2.814670
4-14  3.896470 0.8588376 18 0.2219022 1.845416
4-60  3.931643 0.9610923 18 0.2219022 2.389641
4-7   3.914694 1.0320494 18 0.2219022 2.464104
80-1  3.896385 0.9147642 18 0.2219022 2.225624
CK    4.192620 0.9716571 18 0.2219022 2.958315
           Max      Q25      Q50      Q75
20-14 5.276959 3.230613 3.904684 4.770485
20-60 6.084478 3.250549 3.774614 4.684616
20-7  5.447563 3.225027 4.078337 5.123040
4-14  5.350678 3.467834 4.038940 4.481770
4-60  5.626907 3.505348 3.813338 4.623343
4-7   5.893457 3.161278 3.891053 4.656434
80-1  5.612041 3.197598 3.792232 4.584298
CK    5.857532 3.414184 4.005296 4.997668

$comparison
NULL

$groups
         value groups
CK    4.192620      a
20-7  4.147175      a
20-60 3.995833      a
20-14 3.981813      a
4-60  3.931643      a
4-7   3.914694      a
4-14  3.896470      a
80-1  3.896385      a

attr(,"class")
[1] "group"
```

