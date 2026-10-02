# Student Attendance Prediction

## Project Overview

This project uses machine learning to predict **student attendance percentage** from academic, lifestyle, and demographic factors.

The project was created using **Orange Data Mining**, with no programming required. Multiple regression and tree-based models were tested and compared.

## Objective

The objective of this project is to explore whether student attendance can be predicted using factors such as:

* Study hours per week
* Assignment score
* Previous exam score
* Sleep hours
* Internet usage hours
* Age
* Gender

## Tool Used

* **Orange Data Mining**

## Dataset

The dataset contains student academic and lifestyle information.

### Input Features

| Feature            | Description                  |
| ------------------ | ---------------------------- |
| Age                | Student age                  |
| Gender             | Student gender               |
| StudyHoursPerWeek  | Average study hours per week |
| AssignmentScore    | Assignment performance       |
| PreviousExamScore  | Previous examination score   |
| SleepHours         | Average sleep hours          |
| InternetUsageHours | Internet usage hours         |

### Target Variable

**AttendancePercentage**

`StudentID` was retained as metadata and was not used as a prediction feature.

## Machine Learning Models

Three models were compared:

1. **Linear Regression**
2. **Decision Tree**
3. **Random Forest**

The models were evaluated using Orange's **Test & Score** widget.

## Orange Workflow

The main workflow used was:

```text
File
  ↓
Select Columns
  ↓
Test & Score
  ↓
Predictions
```

The three machine learning models were connected to Test & Score:

```text
Linear Regression ──┐
Decision Tree ──────┼──→ Test & Score
Random Forest ──────┘
```

The selected data was also connected to **Scatter Plot** for visualization.

## Model Results

The following results were obtained from the Orange Data Mining evaluation:

| Model             |   MAE |   RMSE |     R² |
| ----------------- | ----: | -----: | -----: |
| Linear Regression | 7.428 |  9.261 |  0.028 |
| Random Forest     | 8.193 | 10.081 | -0.151 |
| Decision Tree     |     — | 13.221 | -0.980 |

Among the three tested models, **Linear Regression produced the lowest MAE and RMSE** in this evaluation.

The R² values indicate that the selected features did not explain a large proportion of the variation in attendance percentage. The negative R² values for the Decision Tree and Random Forest indicate that they performed worse than the baseline mean prediction in this evaluation.

## Visualizations

The project includes visualizations created using Orange Data Mining.

### Study Hours vs Attendance

This scatter plot explores the relationship between weekly study hours and attendance percentage.

### Previous Exam Score vs Attendance

This scatter plot explores the relationship between previous examination performance and attendance percentage.

### Predictions

The Predictions widget was used to generate predicted attendance values from the tested models.

## Project Files

```text
student-attendance-prediction/
│
├── Student_Attendance_Prediction.ows
├── Images/
│   ├── workflow.png
│   ├── test_score.png
│   ├── study_hours_vs_attendance.png
│   ├── previous_score_vs_attendance.png
│   └── predictions.png
│
└── README.md
```

## Methodology

1. Loaded the student dataset into Orange Data Mining.
2. Selected **AttendancePercentage** as the target variable.
3. Selected academic, lifestyle, and demographic variables as input features.
4. Compared Linear Regression, Decision Tree, and Random Forest models.
5. Evaluated the models using Test & Score.
6. Created scatter plots to explore relationships between variables.
7. Generated attendance predictions using the Predictions widget.
8. Compared the model evaluation metrics.

## Limitations

* The current features explain only a small amount of the variation in attendance.
* The models were evaluated on this particular dataset and may perform differently on other datasets.
* Attendance can be influenced by factors that are not included in the dataset.
* The project is intended as an exploratory machine learning project rather than a production prediction system.

## What I Learned

Through this project, I learned how to:

* Prepare data for machine learning
* Select features and a target variable
* Build machine learning workflows in Orange
* Use Linear Regression, Decision Trees, and Random Forest
* Compare models using MAE, RMSE, and R²
* Create scatter plot visualizations
* Generate predictions
* Interpret model performance and limitations

## Conclusion

This project demonstrates a complete beginner-level machine learning workflow for predicting student attendance using Orange Data Mining.

The evaluation showed that the tested models had limited predictive performance with the selected features. This also demonstrates an important part of machine learning: **evaluating model performance rather than assuming that a model will produce accurate predictions.**
