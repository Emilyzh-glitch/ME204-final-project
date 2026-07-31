---
layout: default
title: Do Major Film Studios Benefit from a "Halo Effect"?
---

```{=html}
<style>
:root{
--heading:#2F6F91;
--accent:#F2C14E;
--border:#E5E5E5;
--text:#333333;
--light:#F7F9FB;
}
html{scroll-behavior:smooth;}
body{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Helvetica,Arial,sans-serif;color:var(--text);line-height:1.8;font-size:18px;}
h1,h2,h3{color:var(--heading);}
img{width:100%;border:1px solid var(--border);border-radius:10px;box-shadow:0 4px 12px rgba(0,0,0,.08);}
figure{margin:2em auto;}
figcaption{text-align:center;color:#666;font-size:.92em;margin-top:.6em;}
.takeaway{background:var(--light);border-left:6px solid var(--heading);padding:16px;border-radius:6px;margin:1.5em 0;}
</style>
```
# ME204 Final Project

- [Emily-glitch](./index.md)

# Do Major Film Studios Benefit from a "Halo Effect"?

When audiences watch a film, are they judging **the film itself**, or
are they also influenced by **the studio logo that appears before the
opening scene**?

Disney. Warner Bros. Universal. These names carry decades of reputation
and may create expectations before a film even begins. This project
explores whether that reputation is reflected in the way audiences and
professional critics evaluate films.

Rather than deciding whether a film is objectively *good* or *bad*, this
project focuses on **disagreement** between audiences and critics.

------------------------------------------------------------------------

# Research Question

> **Do major studio films show larger audience--critic rating gaps than
> non-major studio films?**

Audience ratings were collected from **TMDB**, while professional critic
ratings (Metascore) were collected from **OMDb**.

Throughout this project:

> **Audience--Critic Gap = Audience Score − Critic Score**

Positive values indicate audiences rated a film higher than critics;
negative values indicate critics rated films higher than audiences.

------------------------------------------------------------------------

# Contents

1.  Overall Pattern
2.  Where Does the Difference Come From?
3.  Does Genre Matter?
4.  So What Does This Mean?
5.  Measuring the Data
6.  Limitations
7.  Future Directions

------------------------------------------------------------------------

# Overall Pattern

## Major and non-major films appear broadly similar overall, but differences emerge when disagreement is separated by direction.

::: takeaway
`<strong>`{=html}Key takeaway.`</strong>`{=html} Overall differences are
relatively modest. However, separating positive and negative gaps shows
that the observed difference is mainly driven by cases where critics
rate films more positively than audiences.
:::

```{=html}
<figure>
```
`<img src="assets/overall_gap_boxplot.png" alt="Overall audience–critic gap by studio type">`{=html}
```{=html}
<figcaption>
```
Overall audience--critic gap by studio type.
```{=html}
</figcaption>
```
```{=html}
</figure>
```
Major studio films exhibit a slightly larger average audience--critic
gap, while non-major films display a wider spread, indicating greater
variation.

```{=html}
<figure>
```
`<img src="assets/gap_direction_boxplot.png" alt="Audience–critic gap separated by direction">`{=html}
```{=html}
<figcaption>
```
Audience--critic disagreement separated by direction.
```{=html}
</figcaption>
```
```{=html}
</figure>
```
When audiences rate films more highly than critics, the two studio
groups are broadly similar. In contrast, when critics rate films more
highly than audiences, non-major films show a noticeably larger negative
gap.

------------------------------------------------------------------------

# Where Does the Difference Come From?

## Non-major films are more likely to receive lower audience ratings than critic ratings.

::: takeaway
`<strong>`{=html}Key takeaway.`</strong>`{=html} Non-major films contain
a larger proportion of negative audience--critic gaps and more extreme
disagreements.
:::

### Major Studio Films

```{=html}
<figure>
```
`<img src="assets/hist_major.png" alt="Distribution of gaps for major studio films">`{=html}
```{=html}
<figcaption>
```
Distribution of audience--critic gaps for major studio films.
```{=html}
</figcaption>
```
```{=html}
</figure>
```
### Non-major Studio Films

```{=html}
<figure>
```
`<img src="assets/hist_indie.png" alt="Distribution of gaps for non-major studio films">`{=html}
```{=html}
<figcaption>
```
Distribution of audience--critic gaps for non-major studio films.
```{=html}
</figcaption>
```
```{=html}
</figure>
```
Compared with major studio films, non-major productions contain a
noticeably higher proportion of films where critics rate movies more
positively than audiences, together with more observations at the
extreme ends of the distribution.

------------------------------------------------------------------------

# Does Genre Matter?

## The relationship between studio type and audience--critic disagreement depends on genre.

::: takeaway
`<strong>`{=html}Key takeaway.`</strong>`{=html} Animation exhibits one
of the largest differences between major and non-major films, while
Mystery shows the largest difference in the opposite direction.
:::

```{=html}
<figure>
```
`<img src="assets/genre_gap_comparison.png" alt="Average audience–critic gap by genre">`{=html}
```{=html}
<figcaption>
```
Average audience--critic gaps across genres.
```{=html}
</figcaption>
```
```{=html}
</figure>
```
Some genres display very similar audience--critic patterns regardless of
studio type, whereas others differ considerably, suggesting that genre
influences the relationship.

```{=html}
<figure>
```
`<img src="assets/genre_difference.png" alt="Difference in audience–critic gaps by genre">`{=html}
```{=html}
<figcaption>
```
Difference in average audience--critic gaps between major and non-major
films.
```{=html}
</figcaption>
```
```{=html}
</figure>
```
Animation shows one of the largest differences, with non-major films
exhibiting a larger audience--critic gap. Mystery shows the largest
difference in the opposite direction.

------------------------------------------------------------------------

# So What Does This Mean?

Overall, the analysis provides **some evidence** that studio affiliation
is associated with audience--critic disagreement. However, the effect is
relatively modest and is not consistent across all genres. Rather than
supporting a simple "major versus non-major" explanation, the results
suggest that audience--critic disagreement is shaped by multiple
factors, including genre and film-specific characteristics.

------------------------------------------------------------------------

# Measuring the Data

Two APIs were combined in this project.

-   **TMDB** provided audience ratings, genres, production companies and
    movie metadata.
-   **OMDb** provided professional critic ratings (Metascore).

The datasets were merged using IMDb IDs before feature engineering was
performed to derive audience scores, critic scores, audience--critic
gaps and genre classifications.

------------------------------------------------------------------------

# Limitations

-   Metascore is treated as a professional reference rather than an
    objective measure of film quality.
-   The major/non-major classification simplifies a complex production
    landscape.
-   Some genres contain relatively small sample sizes.
-   Minor inconsistencies exist between TMDB and OMDb release years.

------------------------------------------------------------------------

# Future Directions

Future work could expand studio classifications using more comprehensive
industry databases, incorporate additional explanatory variables such as
marketing expenditure or franchise status, and analyse a larger
collection of films across multiple rating platforms.
