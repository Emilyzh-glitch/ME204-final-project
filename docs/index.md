---
layout: default
title: Major Studios, Indie Films, and Audience–Critic Disagreement
---
# ME204 Final Project

- [Emily-glitch](./index.md)

# Major & Non-major Studios Films, and Audience–Critic Disagreement

## Do major studio films receive more favourable audience evaluations?

Movies are evaluated by two different groups: professional critics and general audiences.

This project explores whether major studio films show different patterns of audience–critic disagreement compared with indie films.

A possible explanation is the existence of a **studio reputation effect**, where audiences may evaluate films differently depending on the perceived credibility or familiarity of the studio behind them.

Rather than assuming that one rating system represents the "true" quality of a film, this analysis treats the difference between audience and critic ratings as a measure of disagreement between two evaluation systems.

The key measure used throughout this project is:

**Audience–Critic Gap = Audience Score − Critic Score**

A positive value indicates audiences rated a film higher than critics, while a negative value indicates critics rated a film higher than audiences.

---

# Key Findings

## 1. Major films show a slightly larger audience–critic gap, while indie films show greater variation

Major studio films have a slightly higher average audience–critic gap compared with indie films.

However, the difference is relatively small. Instead, one noticeable pattern is that indie films display a wider distribution, suggesting greater variation in how audiences and critics evaluate these films.

![Overall audience critic gap comparison](asset/overall_gap_boxplot.png)

---

## 2. Studio differences become clearer when considering the direction of disagreement

The difference between major and indie films depends on whether audiences or critics give higher ratings.

When audiences rate films higher than critics, major and indie films show relatively similar distributions.

However, when critics rate films higher than audiences, indie films show a larger negative gap compared with major studio films.

This suggests that the observed studio difference is mainly driven by cases where audiences are less favourable than critics.

![Audience critic gap direction comparison](asset/gap_direction_boxplot.png)

---

## 3. Indie films contain a higher proportion of cases where audiences rate films below critics

The distribution of rating gaps shows that indie films have a larger share of negative audience–critic gaps.

This indicates that indie films more frequently appear in situations where critic evaluations are more positive than audience evaluations.

At the same time, indie films also show more extreme values, suggesting that audience and critic opinions may diverge more strongly for some indie releases.

Major studio
![Distribution of audience critic gaps](asset/gap_distribution_major.png)

Indie studio
![Distribution of audience critic gaps](asset/gap_distribution_indie.png)
---

## 4. The relationship between studio type and rating disagreement varies across genres

The genre-level analysis shows that differences between major and indie films are not consistent across all genres.

Some genres show relatively small differences, while others show much larger differences in audience–critic gaps.

This suggests that genre characteristics may influence the level of disagreement between audiences and critics.

![Audience critic gap by genre](asset/genre_gap_comparison.png)

---

## 5. Animation and Mystery highlight strong genre-level differences

Among the examined genres, Animation shows one of the largest differences between major and indie films, with indie films exhibiting a larger audience–critic gap.

In contrast, Mystery shows a large difference in the opposite direction, where major studio films have a larger gap.

These results suggest that the relationship between studio type and audience–critic disagreement may depend on genre rather than following one consistent pattern.

![Genre differences in audience critic gap](asset/genre_difference.png)

---

# Overall Interpretation

The findings provide some indication that major studio affiliation may be associated with slightly different audience–critic rating patterns.

However, the effect is relatively modest and varies across genres.

Therefore, the results do not suggest a simple major-versus-indie divide. Instead, audience–critic disagreement appears to be influenced by multiple factors, including film genre and individual film characteristics.

---

# Measuring the Data

## Data Sources

Two APIs were combined in this project:

- **TMDB API** was used to collect movie information, including production companies, genres, release dates, vote counts, and audience ratings.
- **OMDb API** was used to collect critic-related information, including Metascore and IMDb ratings.

The two datasets were merged using IMDb IDs as the unique identifier.

---

## Dataset Construction

The data pipeline consisted of:

1. Collecting major studio and indie film lists from TMDB.
2. Fetching additional movie details from TMDB.
3. Fetching critic information from OMDb using IMDb IDs.
4. Cleaning and combining both datasets.
5. Creating derived variables for analysis.

The final dataset contains:

- movie information
- studio classification
- audience score
- critic score
- audience–critic gap
- genre categories

---

## Studio Classification

Major films were identified based on selected major production companies.

All other films were classified as indie films.

This provides a simplified comparison between films associated with major studios and films outside these major companies.

---

## Data Limitations

Several limitations should be considered:

### Critic score as a quality reference

Metascore represents professional reviews but does not represent an objective measurement of film quality.

The analysis therefore measures differences between audience and critic evaluations rather than absolute film quality.

### Audience score differences across platforms

Audience ratings were estimated using available audience rating sources.

Different platforms may attract different groups of users and may have different rating behaviours.

### Studio classification

The major/indie classification simplifies a complex industry structure.

Some films involve subsidiaries, partnerships, or mixed financing arrangements that may not fit perfectly into either category.

### Sample limitations

Some genres contain fewer observations.

Genres with insufficient sample sizes were removed to reduce instability, but results should still be interpreted carefully.

---

# Future Directions

Future research could improve this analysis by:

## Improving studio classification

A more detailed classification system could include parent companies, subsidiaries, and co-production relationships.

Industry databases or publicly available film resources could be used to build a more comprehensive studio classification.

## Adding additional explanatory variables

Future analysis could include factors such as:

- marketing expenditure
- franchise status
- cast popularity
- social media engagement
- distribution strategy

These variables may help explain why some films produce larger audience–critic disagreements.

## Expanding the dataset

A larger dataset covering more films, years, and platforms could provide stronger evidence about whether studio reputation influences audience evaluation patterns.






