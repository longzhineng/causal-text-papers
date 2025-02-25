# Papers about Causal Inference and Language

A collection of papers and codebases about influence, causality, and language. 

_Pull requests welcome!_



# Datasets and Simulations

| Type | Description |   Code |
|-------|--|----|
|  Semi-simulated    | Given text (amazon reviews), extracts treatments (0 or 5 stars) and confounds (product type), then samples outcomes (sales) conditioned on the extracted treatments and confounds. |    [git](https://github.com/rpryzant/causal-text/blob/main/src/simulation.py)  |
|     Fully synthetic  |   Samples outcomes, treatments, and confounds from binomial distributions, then words from a uniform distribution conditioned on those sampled variables.      |  [git](https://github.com/zachwooddoughty/emnlp2018-causal/blob/master/datasets.py)    |

# Learning resources and blog posts

| Title | Description | Code |
|-------|-------------|------|
|  [Text and Causal Inference: A Review of Using Text to Remove Confounding from Causal Estimates](https://arxiv.org/pdf/2005.00649.pdf) <br> Katherine A. Keith, David Jensen, and Brendan O’Connor   |  Survey of studies that use text to remove confouding. Also highlights numerous open problems in the space of text and causal inference. |      |
|  [Text Feature Selection for Causal Inference](http://ai.stanford.edu/blog/text-causal-inference/) <br> Reid Pryzant and Dan Jurafsky    |   Blog post about text as treatment (operationalized through lexicons)        |   [git](https://github.com/rpryzant/causal_selection)   |
|       |             |      |
|  [Econometrics Meets Sentiment: An Overview of Methodology and Applications](https://doi.org/10.1111/joes.12370) <br> Andres Algaba, David Ardia, Keven Bluteau, Samuel Borms, and Kris Boudt    |   Survey summarizing various methods to transform alternative data (with a focus on text) into a variable, and use it in econometric models. Includes applications throughout.      |   [git](https://github.com/sborms/econometrics-meets-sentiment)   |
|       |             |      |


# Causal  Inference with Text Variables

## Text as treatment


| Title | Description | Code |
|-------|-------------|------|
|  [Causal Effects of Linguistic Properties](https://arxiv.org/pdf/2010.12919.pdf) <br> Reid Pryzant, Dallas Card, Dan Jurafsky, Victor Veitch, Dhanya Sridhar     |    Develops an adjustment procedure for text-based causal inference with classifier-based treatments. Proves bounds on the bias    |   [git](https://github.com/rpryzant/causal-text)   |
|  [Challenges of Using Text Classifiers for Causal Inference](https://arxiv.org/pdf/1810.00956.pdf) <br> Zach Wood-Doughty, Ilya Shpitser, Mark Dredze     |    Looks at different errors that can stem from estimating treatment labels with classifiers, proposes adjustments to account for said errors    |   [git](https://github.com/zachwooddoughty/emnlp2018-causal)   |
|  [Deconfounded Lexicon Induction for Interpretable Social Science](https://nlp.stanford.edu/pubs/pryzant2018lexicon.pdf) <br>  Reid Pryzant, Kelly Shen, Dan Jurafsky, Stefan Wager    |  Looks at effect of text as manifested in lexicons or individual words, proposes algorithms for estimating effects and evaluating lexicons      |   [git](https://github.com/rpryzant/causal_attribution)   |
|  [How to Make Causal Inferences Using Texts](https://arxiv.org/pdf/1802.02163.pdf) <br> Naoki Egami, Christian J. Fong, Justin Grimmer, Margaret E. Roberts, and Brandon M. Stewart     |   (Also text as outcome). Covers assumptions needed for text as treatment and concludes that you should use a train/test set.        |      |
| [Discovery of treatments from text corpora](https://www.aclweb.org/anthology/P16-1151.pdf) <br> Christian Fong, Justin Grimmer| Propose a new experimental design and statistical model to simultaneously discover treatments in a corpora and estimate causal effects for these discovered treatments. | 
| [The effect of wording on message propagation: Topic and author-controlled natural experiments on twitter](https://arxiv.org/pdf/1405.1438.pdf) <br> Chenhao Tan, Lillian Lee, and Bo Pang | Controls for confouding by looking at Tweets containing the same url and written by the same user but employing different wording. | |
| [When do Words Matter? Understanding the Impact of Lexical Choice on Audience Perception using Individual Treatment Effect Estimation](https://arxiv.org/abs/1811.04890) <br> Zhao Wang and Aron Culotta | Measure effect of words on reader's perception. Multiple quasi-experimental methods compared.| [git](https://github.com/tapilab/aaai-2019-words)|

## Text as mediator


| Title | Description | Code |
|-------|-------------|------|
| [Adapting Text Embeddings for Causal Inference](https://arxiv.org/pdf/1905.12741.pdf) <br> Victor Veitch, Dhanya Sridhar, and David Blei      |  (also text as confounder) Adapts BERT embeddings for causal inference by predicting propensity scores and potential outcomes alongside masked language modeling objective.      |  [tensorflow](https://github.com/blei-lab/causal-text-embeddings) <br> [pytorch](https://github.com/rpryzant/causal-bert-pytorch)    |
|       |             |      |

## Text as outcome


| Title | Description | Code |
|-------|-------------|------|
|  [Estimating Causal Effects of Tone in Online Debates](https://arxiv.org/pdf/1906.04177.pdf) <br> Dhanya Sridhar and Lise Getoor    |  (Also text as confounder). Looks at effect of reply tone on the sentiment of subsiquent responses in online debates.         | [git](https://github.com/dsridhar91/debate-causal-effects)     |
|  [How Judicial Identity Changes the Text of Legal Rulings](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2620781) <br> Michael Gill and Andrew Hall |  Looks at how the random assignment of a female judge or a non-white judge affects the language of legal rulings. |      |
| [Measuring semantic similarity of clinical trial outcomes using deep pre-trained language representations](https://www.sciencedirect.com/science/article/pii/S2590177X19300575)<br> Anna Koroleva,  Sanjay Kamath,  Patrick Paroubek ||

## Text as confounder

| Title | Description | Code |
|-------|-------------|------|
| [Text and Causal Inference: A Review of Using Text to Remove Confounding from Causal Estimates](https://arxiv.org/pdf/2005.00649.pdf) <br> Katherine A. Keith, David Jensen, and Brendan O’Connor   |  Survey of studies that use text to remove confouding. Also highlights numerous open problems in the space of text and causal inference. | |
| [Adjusting for confounding with text matching](https://scholar.princeton.edu/sites/default/files/bstewart/files/textmatching_preprint.pdf) <br> Margaret E Roberts, Brandon M Stewart, and Richard A Nielsen |  Estimate a low-dimensional summary of the text and condition on this summary via matching to remove confouding. Proposes a method of text matching, topical inverse regression matching, that matches on both on the topical content and propensity score.||
| [Matching with text data: An experimental evaluation of methods for matching documents and of measuring match quality](https://arxiv.org/pdf/1801.00644) <br> Reagan Mozer, Luke Miratrix, Aaron Russell Kaufman, L Jason Anastasopoulos | Characterizes and empirically evaluates a framework for matching text documents that decomposes existing methods into: the choice of text representation, and the choice of distance metric.||
| [Learning representations for counterfactual inference](http://www.jmlr.org/proceedings/papers/v48/johansson16.pdf) <br> Fredrik Johansson, Uri Shalit, David Sontag | One of their semi-synthetic experiments has news content as a confounder. | |



# Causality to Improve NLP

## Causal interpretations and explanations 

| Title | Description | Code |
|-------|-------------|------|
| [CausaLM: Causal Model Explanation Through Counterfactual Language Models](https://arxiv.org/pdf/2005.13407.pdf) <br> Amir Feder, Nadav Oved, Uri Shalit and Roi Reichart     |  Suggested a method for generating causal explanations through counterfactual language representations.     |  [git](https://github.com/amirfeder/CausaLM)    |
| [Causal Mediation Analysis for Interpreting Neural NLP: The Case of Gender Bias](https://arxiv.org/pdf/2004.12265.pdf) <br> Jesse Vig, Sebastian Gehrmann, Yonatan Belinkov, Sharon Qian, Daniel Nevo, Yaron Singer and Stuart Shieber     |  Uses causal mediation analysis to interpret NLP models.     |  [git](https://github.com/sebastianGehrmann/CausalMediationAnalysis)    |

## Sensitivity and Robustness

| Title | Description | Code |
|-------|-------------|------|
| [Robustness to Spurious Correlations in Text Classification via Automatically Generated Counterfactuals](https://arxiv.org/abs/2012.10040) <br> Zhao Wang and Aron Culotta     |  Matching to identify causal terms, then generate counterfactuals for training. | [git](https://github.com/tapilab/aaai-2021-counterfactuals)|
| [Identifying Spurious Correlations for Robust Text Classification](https://arxiv.org/abs/2010.02458) <br> Zhao Wang and Aron Culotta     |  Matching to identify spurious word features | [git](https://github.com/tapilab/emnlp-2020-spurious)|
| [Discovering and Controlling for Latent Confounds in Text Classification Using Adversarial Domain Adaptation](https://epubs.siam.org/doi/pdf/10.1137/1.9781611975673.34) <br> Virgile Landeiro, Tuan Tran, and Aron Culotta     |  Control for unobserved confounders in text classification      | |
| [Robust Text Classification under Confounding Shift](https://jair.org/index.php/jair/article/view/11248) <br> Virgile Landeiro and Aron Culotta     |  Control for changing confounders in text classification      | [git](https://github.com/tapilab/aaai-2016-robust)|


# Applications in the Social Sciences

## Linguistics 

| Title | Description | Code |
|-------|-------------|------|
| [Decoupling entrainment from consistency using deep neural networks](https://arxiv.org/abs/2011.01860) <br> Andreas Weise, Rivka Levitan     |  Isolated the individual style of a speaker when modeling entrainment in speech.     |     |
| [Estimating causal effects of exercise from mood logging data](https://linqs.soe.ucsc.edu/sites/default/files/papers/sridhar-causalml18_1.pdf) <br> Dhanya Sridhar, Aaron Springer, Victoria Hollis, Steve Whittaker, Lise Getoor |Confouder:  Text of mood triggers. Confounding adjustment method: Propensity score matching ||


## Marketing 


| Title | Description | Code |
|-------|-------------|------|
| [Predicting Sales from the Language of Product Descriptions](https://nlp.stanford.edu/pubs/pryzant2017sigir.pdf) <br> Reid Pryzant, Young-Joo Chung, and Dan Jurafsky     |  Found features of product descriptions most predictive of sales while controlling for brand & price.     |  [git](https://github.com/rpryzant/causal_attribution)    |
| [Interpretable Neural Architectures for Attributing an Ad’s Performance to its Writing Style](https://nlp.stanford.edu/pubs/pryzant2018emnlp.pdf) <br> Reid Pryzant, Kazoo Sone, and Sugato Basu     |   Found features of ad copy most predictive of high CTR while controlling for advertiser and targeting.    |  [git](https://github.com/rpryzant/deconfounded_lexicon_induction/tree/master/text-performance-attribution)    |



## Persuasion & Argumentation

| Title | Description | Code |
|-------|-------------|------|
| [Influence via Ethos: On the Persuasive Power of Reputation in Deliberation Online](https://arxiv.org/pdf/2006.00707.pdf) <br> Emaad Manzoor, George H. Chen, Dokyun Lee, Michael D. Smith |Controls for unstructured argument text using neural models of language in the double machine-learning framework.||
|       |             |      |


## Mental Health 
| Title | Description | Code |
|-------|-------------|------|
| [The language of social support in social media and its effect on suicidal ideation risk](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5565730/) <br> Munmun De Choudhury and Emre Kiciman | Confouder: previous text written in a Reddit forum. Confounding adjustment method: stratified propensity scores matching.   || 
|[Discovering shifts to suicidal ideation from mental health content in social media](https://dl.acm.org/doi/pdf/10.1145/2858036.2858207?casa_token=ZJKLrg8LAOsAAAAA:ecs8HsunRyeUeD_De6Dx15_nPRZ1-mmjiXfAEXLpr25wwz6ywzQcJuZqWjJQIyibEGxZTOkULd1h) <br> Munmun De Choudhury, Emre Kiciman, Mark Dredze, Glen Coppersmith, Mrinal Kumar | Confouder: User’s previous posts and comments received. Confounding adjustment method: stratified propensity scores matching | |

## Psychology


| Title | Description | Code |
|-------|-------------|------|
|  [Increasing vegetable intake by emphasizing tasty and enjoyable attributes: A randomized controlled multisite intervention for taste-focused labeling](https://journals.sagepub.com/doi/pdf/10.1177/0956797619872191)  <br> Bradley Turnwald, Jaclyn Bertoldo, Margaret Perry, Peggy Policastro, Maureen Timmons, Christopher Bosso, Priscilla Connors, Robert Valgenti, Lindsey Pine, Ghislaine Challamel, Christopher Gardner, Alia Crum  |   Did RCT on cafeteria food labels, observing effect on how much of those foods students took.     |      |
| [A social media study on the effects of psychiatric medication use](https://www.aaai.org/ojs/index.php/ICWSM/article/download/3242/3110/) <br> Koustuv Saha, Benjamin Sugar, John Torous, Bruno Abrahao, Emre Kıcıman, Munmun De Choudhury | Confounder: users' previous posts on Twitter. Confounding adjustment method: Stratified propensity score matching.|

## Economics 
| Title | Description | Code |
|-------|-------------|------|
| [A deep causal inference approach to measuring the effects of forming group loans in online non-profit microfinance platform](https://arxiv.org/pdf/1706.02795) <br> Thai T Pham and Yuanyuan Shen | Confounder: Microloan descriptions on Kiva. Confounding adjustment method: A-IPTW, TMLE on embeddings. ||



## Bias and Fairness
| Title | Description | Code |
|-------|-------------|------|
|   [Unsupervised Discovery of Implicit Gender Bias](https://arxiv.org/pdf/2004.08361.pdf) | Propensity score matching and adversarial learning to get a model to focus on bias instead of other artifacts. | |
| [Tweetment Effects on the Tweeted: Experimentally Reducing Racist Harassment](https://link.springer.com/article/10.1007/s11109-016-9373-5)    <br> Kevin Munger  |   Did RCT sending de-escalation messages to racist twitter users, changing the "from" user and observing effects on downstream behavior.     |      |

## Social Media
| Title | Description | Code |
|-------|-------------|------|
| [Estimating the effect of exercising on users online behavior](http://ls3.rnet.ryerson.ca/wiki/images/e/e0/Ossm2017-amin.pdf) <br> Seyed Amin Mirlohi Falavarjani, Hawre Hosseini, Zeinab Noorian, Ebrahim Bagheri| Confounder: Pre-treatment topical interest shift. Confounding adjustment method: Matching on topic models. ||
| [Distilling the outcomes of personal experiences: A propensity-scored analysis of social media](https://dl.acm.org/doi/pdf/10.1145/2998181.2998353?casa_token=U8iCSHz-uGUAAAAA:i9qcF0UCEH-lYKhTE9aA5RNMxFlvqfPW0tiHtUsh_lkmdV1F1O9ko9jPIl_nb8Cx5Rbtf4nn5JGq) <br> Alexandra Olteanu, Onur Varol, Emre Kiciman | Confounder: Past word use on Twitter. Confoundig adjustment method: Stratified propensity score matching. ||
| [Using longitudinal social media analysis to understand the effects of early college alcohol use](http://kiciman.org/wp-content/uploads/2018/10/college_alcohol_tweets_icwsm18e.pdf) <br> Emre Kiciman, Scott Counts, Melissa Gasser |Confounder: Previous posts on Twitter. Confounding adjustment method: Stratified propensity score matching. ||
| [Using Matched Samples to Estimate the Effects of Exercise on Mental Health from Twitter](https://ojs.aaai.org/index.php/AAAI/article/view/9205/9064) <br> Virgile Landeiro and Aron Culotta |Confounder: Gender, location, profile. Confounding adjustment method: Matching. |[git](https://github.com/tapilab/aaai-2015-matching)|

## Law
| Title | Description | Code |
|-------|-------------|------|
| [Everything Has a Cause: Leveraging Causal Inference in Legal Text Analysis](https://aclanthology.org/2021.naacl-main.155.pdf)  <br> Xiao Liu, Da Yin, Yansong Feng, Yuting Wu, Dongyan Zhao | Built causal graphs from legal descriptions automatically, and disambiguated similar charges with the built graphs. Treatment & Confounders: factors from legal descriptions. |[git](https://github.com/xxxiaol/GCI) |
