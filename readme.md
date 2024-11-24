# README: Efficient Data Storage for `customer_train.csv`

## Overview

This project focuses on transforming and optimizing the storage of the `customer_train.csv` dataset for Training Data Ltd., a major online data science training provider. The goal was to enhance the storage efficiency of a large customer dataset to allow faster predictions when training models, while maintaining the quality and integrity of the data.

## Dataset Background

The `customer_train.csv` file contains anonymized information about students enrolled in data science training. The dataset is intended to be used in predictive models that assess whether students are actively seeking new jobs. Efficient storage of this dataset is critical to improving model performance without reducing the size of the data.

## Solution Overview

To optimize the storage of the dataset, the following transformations were applied:

1. **Categorical Columns with Two Categories**:
   - Columns with only two possible values (e.g., gender, job change) were converted to Boolean data types (`bool`) for memory efficiency.

2. **Integer Columns**:
   - Columns that contained only integer values (e.g., experience, last new job) were converted to 32-bit integers (`int32`) to reduce memory usage.

3. **Float Columns**:
   - Columns that contained floating-point values (e.g., city development index, training hours) were converted to 16-bit floats (`float16`), preserving enough precision while reducing memory usage.

4. **Nominal Categorical Data**:
   - Columns containing nominal categorical data (e.g., city, company type) were stored as `category` data types, which efficiently represent categorical variables without the overhead of string types.

5. **Ordinal Categorical Data**:
   - Columns with ordinal categorical data (e.g., education level, company size) were stored as ordered categories to reflect their natural order. This ensures that they are treated properly in predictive models, while saving memory.

## Data Filtering

The dataset was further filtered to include only the students who meet the following criteria:

- **Experience**: Only students with 10 or more years of experience were included.
- **Company Size**: Only students employed at companies with at least 1000 employees were considered.

This filtering ensures that the dataset is focused on more experienced professionals from larger enterprise companies, which aligns with the target recruiter base.

## Columns in `customer_train.csv`

Here is a summary of the columns in the dataset:

- `student_id`: A unique ID for each student.
- `city`: A code for the city the student lives in.
- `city_development_index`: A scaled development index for the city.
- `gender`: The student's gender.
- `relevant_experience`: An indicator of the student's work-relevant experience.
- `enrolled_university`: The type of university course enrolled in (if any).
- `education_level`: The student's education level.
- `major_discipline`: The educational discipline of the student.
- `experience`: The student's total work experience (in years).
- `company_size`: The number of employees at the student's current employer.
- `company_type`: The type of company employing the student.
- `last_new_job`: The number of years between the student's current and previous jobs.
- `training_hours`: The number of hours of training completed.
- `job_change`: An indicator of whether the student is looking for a new job (1) or not (0).

## Conclusion

By applying the appropriate transformations and filtering to the dataset, we have successfully optimized the storage of `customer_train.csv`. This ensures that the dataset is now more efficient in terms of memory usage while preserving the integrity of the data for use in machine learning models. This optimization will help speed up model training and predictions, providing a more scalable solution for future data analysis.
