# Contextual Appropriateness Features and Labels

The contextual appropriateness collection consists of 1,969 pairs of trip descriptors and venue categories as features. In order to enable researchers to train their models using the contextual appropriateness of venues, we created another collection providing ground truth assessments for the contextual appropriateness of the venue categories. It completes the contextual information (i.e., trip type, group type, trip duration) for 10% of the whole TREC collection. This collection contains 760 rows including the features we already created using crowdsourcing and the context-appropriateness labels for venues. The 10% of labeled data allows to model the venues’ contextual appropriateness given the users’ context and to make prediction for the remaining 90% of the data.
Below, you can see a histogram of venue-context appropriateness score ranges. We partition the histogram into 3 parts based on the scores range. Scores below −0.4 represent inappropriateness and score higher than +0.4 represent appropriateness. Scores between −0.4 and +0.4 do not provide much information and show no agreement among assessors (subjective task).

The following table summerizes the statistics of the two crowdsourced datasets: 

    # categories                    179
    # category-context pairs        1969
    # assessments                   11,489
    Average assessment per pair     5.83
    Average assessment agreement    85%
    # full travel annotations       760
    
This dataset is a part of a larger dataset on POI recommendation, which was a TREC track (i.e., Contextual Suggestion). The dataset of POIs and user ratings is available upon request. Please feel free to contact us (mohammad.alian.nejadi@usi.ch) should you need the full dataset.

## Format

Each row of the contextual_features.csv file for contextual features has these fields:

* ID: a unique identifier for the feature
* Trusted Judgements: the number of workers who judged this feature and were trusted
* Appropriateness Score: the level of agreement between workers, which is also the appropriateness score of the feature. This field ranges from -1 to +1 (absolutely inappropriate to absolutely appropriate)
* Category: the venue category for which the feature is calculated
* Context: one the context descriptors for which the feature is calculated

Below is an example row from the feature set:

    ID      Trusted Judgements      Appropraiteness Score      Category    Context
    85      7                       0.4272                     Museum      Group type: Friends    
      
Furthermore, each row of contextual_training_data.csv for contextual labels has these fields:

* ID: a unique identifier for the sample
* Trusted Judgements: the number of workers who judged this sample and were trusted
* Appropriateness Score: the level of agreement between workers, which is also the appropriateness score of the sample. This field ranges from -1 to +1 (absolutely inappropriate to absolutely appropriate)
* Category: the venue category for which the sample is labeled
* Full Context: the full context description for which the sample is annotated

Below is an example row from the contextual labels:

    ID      Trusted Judgements      Appropraiteness Score      Category    Full Context
    60      4                       1                          Park        Holiday, Friends, Night out
    
## Citation

    @inproceedings{AliannejadiSigir17b,
          author    = {Mohammad Aliannejadi and Ida Mele and Fabio Crestani},
          title     = {A Cross-Platform Collection for Contextual Suggestion},
          booktitle = {{SIGIR}},
          pages     = {1269--1272},
          publisher = {{ACM}},
          month = {August},
          year      = {2017}
        }
