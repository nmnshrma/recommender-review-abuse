# Measuring Recommender Systems robustness against review abuse

## Project:

Evaluation Bias amongst long-time readers towards favored authors

## Project Goals & Motivation:

The primary objective of the research to evaluate confirmation biases amongst real world users. At this stage, the project aims to develop metrics to aptly identify these biases and their effects. The research's other motive is to create accessible research, that can be understood by experts in fields not related to machine learning.

### Problem Statement:
To quantifiably prove assessment and evaluation biases amongst long-time readers of authors using the [Amazon Review Dataset](https://nijianmo.github.io/amazon/index.html) (Julian McAuley et al.<sup>[1]</sup>). The project is intented to produce principled, verifiable research that aims to quantify human biases in a (very narrow) space, which are, book reviews across the amazon and kindle platform.

__Research Question 1.1: What is the impact of cognition biases amongst reviewers on the author ratings on Amazon__

* __Hypothesis__: Ardent promoters and detractors for an author lead to significant inflated and deflated ratings for the author, and/or their work.

* __Methodology/Plan__:
   Identification of users that consistently 'upvote'

__Research Question 1.2: Building upon RQ1.1, what is the scale of the distortion in user level recommendations__

* __Hypothesis__: The inflated/deflated ratings for particular authors and works lead to significantly distorted recommendations at any point in time.

* __Methodology/Plan__:
    
    1. Collaborative Filtering, Item-Item Recommendation
    2. Collaborative Filtering, User-Item Recommendation
    3. Clustering (kNN) models
    4. Singular Vector Decomposition, or SVD, models

__Unknowns and dependencies__:
1. Exhaustiveness of data is unconfirmed by the author
2. Point in time calculations will need significant compute power

## Data Source

The partial dataset is the key data source for the project. An extension of the research questions may be applied to the metadata.

Note: The dataset hosted in the project will represented 5% representative sample drawn from the original dataset, after due permission from the team that worked on gathering the source dataset, i.e., Juliam McAuley et al.

The data is split into two parts:
1. __The Review Data__: The key raw fields for the reviews and ratiings
2. __The Metadata__: Aggregated data, containing additional information about the review

__1. Review Data__:

| ID | Field          | Description                                                          | Type                 |
|----|----------------|----------------------------------------------------------------------|----------------------|
| 1  | reviewerID     | A Unique ID of the reviewer, on amazon.com                           | string               |
| 2  | asin           | Unique Product ID                                                    | string               |
| 3  | reviewerName   | Reviewer Name                                                        | string               |
| 4  | vote           | Helpful Votes                                                        | int                  |
| 5  | style          | a disctionary of the product metadata, e.g., "Format" is "Hardcover" | dict                 |
| 6  | reviewText     | Blob text of the review                                              | blob text            |
| 7  | overall        | product rating                                                       | float                |
| 8  | summary        | summary of the review                                                | string               |
| 9  | unixReviewTime | time of the review (unix time)                                       | int                  |
| 10 | reviewTime     | time of the review (raw)                                             | string "mm dd, yyyy" |

__2. Metadata__:

| ID | Field       | Description                                                                     | Type      |
|----|-------------|---------------------------------------------------------------------------------|-----------|
| 1  | asin        | ID of the product, e.g. 0000031852                                              | string    |
| 2  | title       | name of the product                                                             | string    |
| 3  | feature     | bullet                                                                          | list      |
| 4  | description | description of the product                                                      | blob text |
| 5  | price       | price in US dollars (at time of crawl)                                          | float     |
| 6  | imUrl       | url of the product image                                                        | string    |
| 7  | related     | related products (also bought, also viewed, bought together, buy after viewing) | dict      |
| 8  | salesRank   | sales rank information                                                          | dict      |
| 9  | brand       | brand name                                                                      | string    |
| 10 | categories  | list of categories the product belongs to                                       | list      |

## License

The dataset is openly available for use and experimentation. The complete dataset can be accessed upon request from the team. Citation is needed in both cases.

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/nmnshrma/data-512-project/blob/master/LICENSE) file for details

## Acknowledgments & Citations:

1. Justifying recommendations using distantly-labeled reviews and fined-grained aspects (Data Source)
Jianmo Ni, Jiacheng Li, Julian McAuley
_Empirical Methods in Natural Language Processing (EMNLP), 2019_, [pdf](http://cseweb.ucsd.edu/~jmcauley/pdfs/emnlp19a.pdf)
