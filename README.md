# fake-reviews-data
This data contains a large set of Amazon product reviews collected in 2019-2020. Using a combination of direct evidence and classification, individual reviews are labeled as "fake" or not, where fake in this case means the reviewer was recruited and paid by the seller to purchase the product and write a positive review. More details on the nature of fake review transactions are detailed in He et al (2022a). 

This data can be used to study the characteristics (linguistics or otherwise) of fake vs real reviews and to assess proposed fake review detection methods.

Data can be downloaded from either:

https://bretthollenbeckcom.wordpress.com/wp-content/uploads/2025/07/public_reviews_dataset.json_.zip
https://bretthollenbeckcom.wordpress.com/wp-content/uploads/2025/07/public_reviews_dataset.csv_.zip

The file public_reviews_data.csv contains the following variables:

fake_review_campaign_start_date: taken from He et al (2022a), this measures the first observed Facebook post by the seller recruiting fake reviews. It is an imperfect measure of the beginning of a fake review campaign that can contribute to the ground truth of what reviews are real/fake, since a review posted before this date is less likely to be fake.

Fake_review_product: Classification results from He et al (2022b), who classify products as using or not using fake reviews based on features of the reviewer-product network and other features. 

reviewer_classified_fake: Classification results from Feldman et al (2025), who classify reviewers based on relational patterns in reviewer behavior.

reviewer_classified_real: Inverse of above. Note that not all reviewers have sufficient data for classification.

Reviewer_label: This labels reviewers as real/fake using pre-specified rules as detailed in Feldman et al (2025) and acts as the basis for training their classification model.

Deleted_by_amazon: Uses data from Hou et al (2024) to denote which reviews were deleted by Amazon at some point between 2020 and 2023. This can either contribute to ground truth labeling of reviews or can be used to compare proposed classification methods to Amazon’s internal practices.

These variables can be combined to construct a ground truth labeling of reviews as real/fake for model training or feature comparisons. For example, a review may be labeled “fake” if it is a 5-star review of a fake review purchasing product written by a fake reviewer. Stricter criteria could also be applied, using the date or "deleted by Amazon" variable. Reviews may be labeled as “real” if they are non-5-star reviews, or are written by non-fake reviewers, or are posted on non-fake review products. Additional criteria can be applied or these can be combined to form a stricter set of “real” reviews for comparisons. 

If using these data, please consider citing some or all of the following, as relevant:

“Detecting Fake Review Buyers Using Network Structure: Direct Evidence from Amazon,”
Sherry He, Brett Hollenbeck, Gijs Overgoor, Davide Proserpio, and Ali Tosyali, 
Proceeedings of the National Academy of Sciences, Vol. 119 (47), 2022, https://doi.org/10.1073/pnas.2211932119

"Addressing Large-scale Reviewer Recruitment on Amazon: A Reviewer-centric Approach to the Fake Review Problem"
Ethan Feldman, Ali Tosyali, Gijs Overgoor, 2025, http://dx.doi.org/10.2139/ssrn.5156231

“The Market for Fake Reviews”
Sherry He, Brett Hollenbeck, and Davide Proserpio 
Marketing Science, 2022, Vol.41(5), p.896-921, https://doi.org/10.1287/mksc.2022.1353

"Bridging Language and Items for Retrieval and Recommendation"
Yupeng Hou, Jiacheng Li, Zhankui He, An Yan, Xiusi Chen, Julian McAuley, 
https://doi.org/10.48550/arXiv.2403.03952



