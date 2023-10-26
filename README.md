![christian-lue-8Yw6tsB8tnc-unsplash](https://github.com/KarlHampusLarsson/trust-in-europe/assets/111912321/9143108b-41a8-4c56-a8a8-ac2aa303f252)

# Trust among European Citizens: a Multivariate Analysis

## Project overview
Trust is the firm belief in the  reliability, truth or ability of someone or something. The goal of this project was to explore trust among European citizens; to see what they trust and to what extent. There seem to be three underlying levels of trust: interpersonal, national and international. Europeans also seem to be able to be grouped as low-, medium- and high-trust individuals. This project was performed as an assignment for the class Multivariate Methods at Stockholm University. 

## Requirements
- **Language:** R
- **Editor:** RStudio using Rmarkdown.
- **Packages:** _Tidyverse_ for data cleaning, _corrplot_ for correlation plots and _factoextra_ for cluster visualization.

## Data

### Data source
The data used is from the 10th edition of the  [European Social Survey](https://www.europeansocialsurvey.org/), the largest survey in Europe on social attitudes. Respondents are surveyed on their living conditions, attitudes and opinions on varying topics. All variables were measured on a 10-point scale where 1 indicated "No trust" and 10 indicated "High trust".

### Data preprocessing
For the project I included questions related to trust in other people, politicians, political actors and institutions as variables for analysis. The data cleaning needed was to treat non-responses, "Don't know"- and "Refuse to answer"-responses as not available (NA) values and removing them. After cleaning the data contained 33170 observations.

## Code structure
I wrote the project as a report using Rmarkdown. The code was structured in R code chunks in between the text of the report. 

**Example code chunk**
```{r correlation, echo=FALSE}
corr_plot <- round(cor(trust, use="complete.obs"), 2)
print(corr_plot)
corrplot(cor(trust, use="all.obs"), order="original", tl.col="black", tl.cex=0.75)
```

**Output: Correlation matrix of trust-related variables**
![Trust correlations](https://github.com/KarlHampusLarsson/trust-in-europe/assets/111912321/8f8b29fb-6365-41c1-8da4-496e09aee1ed)

The full code can be find find this this file: 

## Approach
### Factor analysis
First I examined if there were any correlations between the trust-related variables, which there seemed to be. I developed three models with different amounts of factors: one, two and three factors. After comparison the three-factor model seemed to explain trust among the respondents best. It had the lowest error rate allowing for more accurate interpretation. The three factors of the model were interpersonal, national and international trust.

### Cluster analysis
Second I grouped the respondents using cluster analysis, specifically k-means. After examining how many clusters seemed appropriate I compared a two-cluster model with a three-cluster one. The three-cluster model explained more of the variance among the data and had tighter clusters allowing for more accurate analysis. The three groups were low-, medium- and high-trust individuals. 

## Results
Whether Europeans trust something seems to partially be explained if it is an individual, a national institution or international institution. They can also be grouped as trusting on varying levels, where people with low trust for other individuals also don't trust politicians and institutions. The same is true for high-trust individuals. If they trust the European Parliament they are for example also likely to trust the United Nations.
 
These findings can be used policy makers to make informed decisions about and develop strategies on trust-building within and among European countries. Key groups with little trust for policy makers can be identified. Organisations doing opinion polling can also use this project to analyze correlations between trust and political opinions. 

## Credits
Image by [Christian Lue on Unsplash](https://unsplash.com/photos/blue-and-yellow-star-flag-8Yw6tsB8tnc?utm_content=creditShareLink&utm_medium=referral&utm_source=unsplash).

The professor for Multivariate Methods Fall 2023 was [Johan Koskinen](https://github.com/johankoskinen) who taught me the methods used and provided  feedback on the project. 
