# Course Recommendation System Project

## Overview
This project aims to create a recommendation system for online courses using the **Coursera Course Dataset**. The system helps users discover courses that are similar to a given course based on various features like course ratings, organizations, certificate types, and difficulty levels.

## Objective
The main objective of this project is to build a content-based recommendation engine that suggests similar courses when a user selects a specific course. This can enhance the course discovery process for learners.

## Dataset
The project uses the **Coursera Course Dataset** available on Kaggle. The dataset includes the following columns:
- `course_title`: The title of the course
- `course_organization`: The organization offering the course
- `course_Certificate_type`: The type of certificate provided
- `course_rating`: The course rating
- `course_difficulty`: The difficulty level of the course
- `course_students_enrolled`: The number of students enrolled in the course

## Methodology
### 1. Data Preparation
- Loaded the data using Pandas and performed an initial inspection.
- Dropped the `Unnamed: 0` column as it was redundant.
- Converted the `course_students_enrolled` column to a numeric format by handling suffixes ('k' for thousands, 'm' for millions) using a custom function.

### 2. Feature Engineering
- One-hot encoded the categorical features (`course_organization`, `course_Certificate_type`, `course_difficulty`) using `OneHotEncoder` from `scikit-learn`.
- Combined the one-hot encoded features with the numerical feature (`course_rating`) to create a feature set for similarity computation.

### 3. Model Implementation
- Used **cosine similarity** to measure the similarity between courses based on the encoded feature set.
- Created a cosine similarity matrix to store the pairwise similarities between all courses.

### 4. Recommendation Function
Defined a function, `recommend_courses(course_title, num_recommendations=5)`, that:
- Takes a course title as input.
- Retrieves the similarity scores from the cosine similarity matrix.
- Sorts and returns the top `num_recommendations` most similar courses.

### Example Output
Given an input course title such as **"Introduction to Data Science"**, the system might return:
- Data Science Fundamentals
- Applied Machine Learning
- Python for Data Science
- Big Data Analysis
- Statistical Inference


## Deployment 
The project can be deployed as a web application using frameworks like **Streamlit**, allowing users to input a course title and receive a list of similar courses.


