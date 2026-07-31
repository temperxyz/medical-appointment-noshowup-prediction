# medical-appointment-noshowup-prediction
# Medical Appointment No-show Prediction

This project is my practice with classification models using the Kaggle Medical Appointment No Shows dataset.

## What I did
- Cleaned the data, removed negative ages and rows with negative waiting days
- Combined the different Handicap levels into one Handicap_flag column since the higher levels had very few rows
- Created a WaitingDays column from the gap between ScheduledDay and AppointmentDay
- Grouped the neighborhoods into top 10 plus an Others category to reduce the number of columns
- Added AppointmentDayofWeek to check if the day of the week matters
- Built a Logistic Regression model with class_weight balanced
- Built a Random Forest model with class_weight balanced and compared it to Logistic Regression
- Looked at feature importance from the Random Forest model

## Results
- Logistic Regression ROC AUC: 0.66
- Random Forest ROC AUC: 0.68
- Random Forest performed a bit better on ROC AUC and recall for the no show class

## Dataset
[Medical Appointment No Shows dataset on Kaggle](https://www.kaggle.com/datasets/joniarroba/noshowappointments)

## What I learned
No show is an imbalanced problem, about 80% of people show up and 20% do not, so I used class_weight balanced on both models instead of just looking at accuracy. Random Forest did better than Logistic Regression here, probably because it can pick up on interactions between features like waiting days and day of week that a linear model cannot capture as well.
