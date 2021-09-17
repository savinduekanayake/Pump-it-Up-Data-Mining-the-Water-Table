# Pump-it-Up-Data-Mining-the-Water-Table


## Loading data

* Read the given csv files.
* Combine the labels with train data.
* Check the duplicates and drop it.
* I removed the lables and combine train dataset and test dataset.


## Plotted the features

* Plotted the features for identifyy the correlations among the features and get to know about the distribution of the features.

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

*	Public_meeting and permit features are simply imputed with the mode.

*	`Funder` and `installer` have ‘0’, ‘-‘and some other irrelevant character except to the nan values. So firstly nan values imputed with mode and the other irrelevant values in those columns are imputed with ‘other’ category

*	`subvillage` and `scheme_management` are grouped by `region_code` and imputed the nan values with mode.

*	`scheme_name` grouped by `region` and imputes the nan values with the mode.

![PopCritic Search](https://raw.githubusercontent.com/theabbie/PopCritic/master/Images/review.JPG)



## NaN imputation

* Node.JS
* PostgreSQL
* React.JS

## Entity-Relationship Diagram

![PopCritic Search](https://raw.githubusercontent.com/theabbie/PopCritic/master/Images/ERD.png)

## Try Locally

Go to `web/popcritic` and run,

```sh
npm install
npm run start
```

## Team
