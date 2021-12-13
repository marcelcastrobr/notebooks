---
toc: true
layout: post
description: Using github actions to create a CICD data pipeline in snowflake data.
title:  "Machine Learning Model Monitoring"
date:   2021-12-13 11:19:07 +0200
categories: ML, data drift, model drift, MLOps


---

# Machine Learning Model Monitoring

![MLOps. You Desing It. Your Train It. You Run It.](https://github.com/visenger/awesome-mlops/blob/master/awesome-mlops-intro.png)

# Why monitoring matters:

Machine learning model monitoring is important as it allows to check for changes on the model performance. It is a cyclical and interactive process and need also to consider the monitoring of the infrastructure such as database and application.

 Model monitoring should account for:

- Data skews

- Model staleness

- Negative feedback loops

  

Functional and non-functional monitoring points are:

- Functional:
  - Predictive peformance
  - Changes in serving data
  - Metrics used during training
  - Characteristics of features
- Non-functional
  - System performance
  - System status
  - System reliability



# Concepts

### Data Skew:

 Data skews occurs when the model training data is not representative of the live data. There are several reasons for data skew, such as:

- Training data was designed wrong such as the distribution of the features in the training is different from the distribution of the features in real life data.
- Feature not available in production

### Model Staleness

Model staleness can occur based on:

- Shifts in the environment as historic data used during model training may change as time progress (e.g. financial models using time of recession might not be effective for predicting default when economy is healthy). 
- Consumer behaviour change such as trends in politics, fashion, etc.
- Adversarial scenarios where bad actors (e.g. criminals) seek to weaken the model. 

### Negative feedback loops

Negative feedback loop arises when you train data collected in production that can lead to bias.



# What and How to Monitor in ML models:



WHAT should we monitor in an ML model in production:

- Model input distribution
  - Errors: input values fall within an allowed set/range? 
  - Changes: does the distribution align with what was seen during training? 
- Model prediction distribution 
  - Statistical significance: e.g. if variables are normally distributes, we might expect the mean values to be within the standard euro of the mean interval.
- Model versions
- Input/prediction correlation



HOW should we monitor it:

- Tracing your ML model through logging. 
  - Observability of ML model while logging distributed tracings might be challenging. However, tools like Dapper, Zipkin and Jaeger could help to do the job.





# References:

[[1] Deploying Machine Learning in Production, Deeplearning](https://www.coursera.org/learn/deploying-machine-learning-models-in-production/lecture/Bew5j/why-monitoring-matters)

[[2] MLOps: What It Is, Why It Matters, and How to Implement It]()

[[3] Awesome MLOps](https://github.com/visenger/awesome-mlops)

