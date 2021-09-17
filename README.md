# Pump-it-Up-Data-Mining-the-Water-Table

## Evaluated and tested models

* `Random Forest`
* `XGboost`
* `Catboost `

## Loading data

* Read the given csv files.
* Combine the labels with train data.
* Check the duplicates in training set and drop it.
* I removed the lables in training set and combine train dataset and test dataset.


## Plotted the features

* Plotted the features for identify the correlations among the features and get to know about the distribution of the features.

## Nan value imputation

* I checked the nan values and founded below counts of nan values for relavent features.

```sh
funder                    4504

installer                 4532

subvillage                 470

public_meeting            4135

scheme_management         4846

scheme_name              35231

permit                    3793
```

*	`Public_meeting` and `permit` features are simply imputed with the mode.

*	`Funder` and `installer` have ‘0’, ‘-‘ and some other irrelevant character except to the nan values. So firstly nan values imputed with mode and the other irrelevant values in those columns are imputed with ‘other’ category

*	`subvillage` and `scheme_management` are grouped by `region_code` and imputed the nan values with mode.

*	`scheme_name` grouped by `region` and imputes the nan values with the mode.

<!-- ![PopCritic Search](https://raw.githubusercontent.com/theabbie/PopCritic/master/Images/review.JPG) -->


## Removed the 0 values of selected features 

* Some features have 0 values which is not compatible for the feature and that hurt the accuracy. So I replaced the 0 value with the mean.

## Outlier detection and corrected values 

*	In the `longitude` and `latitude` there is an outlier which hurt the performance seriously. Which is (0,0) coordinate. I replace that latitude and longitude values group by the `region_code` and using the mean of it.


## One-hot encoding

* I did one-hot encoding for the categorical values and check the correlation with the output. Then I selected the most corelated features.

## Normalize the data

* I tried with different normalization techniques like `log normalization` and `min-max normalization`. 
* I selected some features for the normalization.
* I founded out `log normalization` better performance for `population`.
* I used `min-max normalization` for the `amount_tsh` and `gps_height`

## Evaluation

*	For the evaluation I split the train dataset `train : Val as 90% : 10%`.
*	Then I evaluated `Random Forest, XGBoost and CatBoost`
*	In the evaluation `CatBoost model` perform the heights results repeatedly and also `XGBosst model` also gave more closer results but `Random Forest model` gave less results related to other models.
*	I checked accuracy and plotted the confusion matrix for look more details.

## Testing

* For the testing I re-train the model for all training data and predicted using the given test data for both` XGboost` and `CatBoost` models. Not use random forest because of low accuracy for evaluation.
* I got best accuracy by the `CatBoost model` for the testing
