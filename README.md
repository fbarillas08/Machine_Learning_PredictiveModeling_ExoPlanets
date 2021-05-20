# machine-learning_challenge
Evaluation of several categorization algorithms on NASA's Exoplanet Kepler Dataset

This project evaluates several categorization techniques including:

  - Logistic Regression
  - KNN
  - Random Forest
  - Grid Search

The initial step was eliminating co-dependent variables/measures from the original dataset.  This was done through a study of the data dictionary on the website where the dataset resided.

The next step was the exploration of the data. For each of the three labels: Confirmed, Candidate, and False-Positive there is a boxplot per selected variable.  This analysis is included in the jupyter notebook called boxplots and ExploreData.   The boxplots were used to visually understand the relations between each of the measures and the three labels.

The following are the take-aways from this analysis.  The list shows the measure and what label appears to be more sensitive to it.

  koi_period    -> Candidate
  
  koi_time0bk   -> Confirmed
  koi_impact    -> Confirmed
  koi_tec_plnt_num -> Confirmed
  koi_depth     -> Confirmed
  
  koi_duration  -> False-Positive  
  koi_prad      -> False-Positive
  koi_tec       -> False-Positive
  koi_snr       -> False-Positive
  koi_srad      -> False-Positive
  
  koi_insol     -> NONE
  koi_steff     -> NONE
  koi_slagg     -> NONE
  kep_mag       -> NONE
  va            -> NONE
  dec           -> NONE
  
The potential implication of the analysis above is that any categorization algorithm is more likely to be better at identifying False-Positive label than any of the other two labels.  This was verified in all the algorithms (models) used.

The worst performing algorithm was Logistic Regression with an overall effectiveness of 60%.  However, when a more detailed view of the prediction vs actual results was made. Logistic Regression had an effectiveness of 80% in identifying False Positives, a 60% of Confirmed, and only a 3% effectiveness in identifying Candidates.

The remaining algorithms were comparably effective (92% - 96%) across the board, although accurary (recall) of Candidates was the lowest for all of them.

There was a large computational cost with the Grid Search. The process had to be re-started several times to ensure processing of all the folds.

It was important to eliminate irrelevant or non-significant attributes of measure to ensure the models had a stron base to train the model and effectively do testing and then predictions.
