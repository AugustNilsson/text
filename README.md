
<!-- README.md is generated from README.Rmd. Please edit that file -->

# text

<!-- badges: start -->

<!-- badges: end -->

The language that individuals use contains a wealth of information
interesting for research. *Text* analyzes and visualizes text, and their
relation to other text or numerical variables. The r-package is based on
state-of-the-art techniques from statistics and artificial intelligence,
including natural language processing, deep learning and machine
learning.

*Text* is created through a collaboration between psychology and
computer science to address research needs and ensure state-of-the-art
techiniques. It provides powerful functions tailored to test research
hypotheses in social and behaviour sciences for both relatively small
and large datasets.

### Short installation guide

Most users simply need to run below installation code. For those
experiencing problems, please see the [Extended Installation
Guide](https://www.r-text.org/articles/Extended%20Installation%20Guide.html).

[CRAN](https://CRAN.R-project.org) version:

``` r
install.packages("text")
```

[GitHub](https://github.com/) development version:

``` r
# install.packages("devtools")
devtools::install_github("oscarkjell/text")
```

### Map your text to numbers

Recent significant advances in NLP research have resulted in improved
representations of human language (i.e., language models). These
language models have produced big performance gains in tasks related to
understanding human language. Using deep learning to model word order
and context now gives great results. Multilingual language models can
also represent several languages; multilingual BERT comprises *104
different languages*. Text are making these SOTA models easily
accessible through an interface to
[HuggingFace](https://huggingface.co/transformers/) in Python.

*Table 1. Some of the available language models*

| model\_short    | tokenizer\_short    | pretrained\_weights\_shortcut\_short |
| :-------------- | :------------------ | :----------------------------------- |
| BertModel       | BertTokenizer       | ‘bert-base-uncased’                  |
| BertModel       | BertTokenizer       | **‘bert-multilingual-uncased’**      |
| XLNetModel      | XLNetTokenizer      | ‘xlnet-base-cased’                   |
| DistilBertModel | DistilBertTokenizer | ‘distilbert-base-cased’              |
| RobertaModel    | RobertaTokenizer    | ‘roberta-base’                       |

See [HuggingFace’s Github](https://github.com/huggingface/transformers)
for a more comprehensive list of models.

### An end-to-end package

Text also provides functions to analyse the word embeddings, with
well-tested machine learning algorithms and statistics. An example is
how it is possible to plot statistically significant words in the word
embedding space.

``` r
library(text)
#> [0;32mThis is text (version 0.6.0.9000).[0m
#>  [0;34mNewer versions may have updated default settings to reflect current understandings of the state-of-the-art.[0m
# Use data (DP_projections_HILS_SWLS_100) that have been pre-processed with the textProjectionData function

# The test-data included in the package is called: sq_data_tutorial_plotting_hilswl
plot_projection <- textProjectionPlot(
  word_data = DP_projections_HILS_SWLS_100,
  k_n_words_two_test = TRUE, 
  plot_n_words_square = 3,
  plot_n_words_p = 3,
  plot_n_word_extreme = 1,
  plot_n_word_frequency = 1,
  plot_n_words_middle = 1,
  x_axes = "dot.x",
  y_axes = "dot.y",
  p_values_x = "p_values_dot.x",
  p_values_y = "p_values_dot.y",
  p_alpha = 0.05,
  title_top = " Dot Product Projection (DPP) of Harmony in life words",
  x_axes_label = "Low vs. High HILS score",
  y_axes_label = "Low vs. High SWLS score",
  p_adjust_method = "bonferroni",
  scale_x_axes_lim = c(-15, 15),
  scale_y_axes_lim = c(-15, 15),
  y_axes_values_hide = FALSE
)
plot_projection
```

<img src="man/figures/README-DPP_plot-1.png" width="100%" />

### References

Selected articles analysing human language using (decontextualized) word
embeddings.

***Methods Articles***  
[Gaining insights from social media language: Methodologies and
challenges](http://www.peggykern.org/uploads/5/6/6/7/56678211/kern_2016_-_gaining_insights_from_social_media_language-_methodologies_and_challenges.pdf).  
*Kern et al., (2016). Psychological Methods.*

[Semantic measures: Using natural language processing to measure,
differentiate, and describe psychological
constructs.](https://www.ncbi.nlm.nih.gov/pubmed/29963879)
[Pre-print](https://psyarxiv.com/er6t7/)  
*Kjell et al., (2019). Psychological Methods.*

***Clinical Psychology***  
[Facebook language predicts depression in medical
records](https://www.pnas.org/content/115/44/11203)  
*Eichstaedt, J. C., … & Schwartz, H. A. (2018). PNAS.*

***Social and Personality Psychology***  
[Personality, gender, and age in the language of social media: The
open-vocabulary
approach](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0073791)  
*Schwartz, H. A., … & Seligman, M. E. (2013). PloSOne.*

[Automatic Personality Assessment Through Social Media
Language](https://www.semanticscholar.org/paper/Automatic-personality-assessment-through-social-Park-Schwartz/280034e01f41d0184b977479a5474bd805c2922c)  
*Park, G., Schwartz, H. A., … & Seligman, M. E. P. (2014). Journal of
Personality and Social Psychology.*

***Health Psychology***  
[Psychological language on Twitter predicts county-level heart disease
mortality](https://journals.sagepub.com/doi/abs/10.1177/0956797614557867)  
*Eichstaedt, J. C., Schwartz, et al. (2015). Psychological Science.*

***Positive Psychology***  
[The Harmony in Life Scale Complements the Satisfaction with Life Scale:
Expanding the Conceptualization of the Cognitive Component of Subjective
Well-Being](https://link.springer.com/article/10.1007/s11205-015-0903-z)  
*Kjell, et al., (2016). Social Indicators Research*

***Computer Science: Python Software***  
[DLATK: Differential language analysis
toolkit](http://aclweb.org/anthology/D17-2010)  
*Schwartz, H. A., Giorgi, et al., (2017). In Proceedings of the 2017
Conference on Empirical Methods in Natural Language Processing: System
Demonstrations*

[DLATK](http://dlatk.wwbp.org/)
