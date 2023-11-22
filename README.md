# Road Safety Forecasting: Predictive Modeling of Accident Severity in Addis Ababa
## Report compiled by :
1. Bonventure Osoro.
2. Brian Kipkorir.
3. Jacinta Fiona.
4. James Murigi.
5. Sandra Luyali.
6. Faith Nyawira.
## Report Overview.
1. Business Understanding
2. Data Understanding
3. Data Cleaning and Formating
4. EDA
5. Modeling
6. Model Refinement and Evaluation
7. Summary.
8. Recommendations.
### a. Introduction.

In a metroplitan setting, road accidents cast a far-reaching impact on both individuals and the urban fabric. As cities evolve with complex road networks and diverse transportation modes, the urgency to address road safety intensifies. Crucially, accurate classification of accident severity—spanning 'Slight Injury' and 'fatal Injury' is pivotal. This classification empowers urban planners, law enforcement, emergency responders, and policymakers to strategically allocate resources, enhance safety measures, and optimize emergency responses. Through data-driven insights and predictive modeling, our project aims to contribute to a safer urban landscape, where road safety remains an integral component of urban evolution.

For our project we will assume that we have three clients:
1. Addis Ababa urban planing institute
2. Addis Ababa emergency services
3. Addis Ababa Road Safety Authority
### Problem Statement

In Addis Ababa's dynamic urban landscape, ensuring public safety and efficient resource allocation is a top priority. Classifying road traffic accidents into 'Slight Injury' and 'Serious Injury' categories offers actionable insights for informed decision-making and targeted interventions.

1. The Addis Ababa Urban Planning Institute aims to enhance safety by identifying high-risk zones through accurate accident severity classification, influencing road design and traffic flow management.

2. Emergency services require rapid response and resource allocation. Quick accident severity classification empowers responders to deploy resources promptly, potentially saving lives.

3. The Addis Ababa Road Safety Authority seeks to reduce accidents and their consequences. Precise accident severity classification aids in assessing safety measures and formulating effective policies.

In conclusion, precise classification of road traffic accidents empowers stakeholders to enhance safety and response strategies, contributing to a safer Addis Ababa.
### c. Objectives.

Based on the our problem statement, here are the five objectives for the project:

1. **Create Accurate Classification Model:** Develop a robust predictive model using multi-class classification to accurately categorize road accidents as 'Slight', 'Serious', or 'Fatal'.

2. **Enhance Model Precision:** Rigorously evaluate and refine the model's accuracy through comprehensive testing and data-driven adjustments.

3. **Inform Urban Planning Decisions:** Provide actionable insights to the Urban Planning Institute for identifying high-risk zones, improving safety measures, and aligning urban development strategies.

4. **Optimize Emergency Response:** Empower emergency services with rapid, accurate severity assessments to optimize resource allocation and response effectiveness.

5. **Shape Road Safety Initiatives:** Assist the Road Safety Authority in evaluating measures, crafting targeted awareness campaigns, and formulating policies tailored to different accident scenarios.

6. **Promote Safer Urban Environment:** Contribute to safer roads and an enhanced urban environment by minimizing accident impact and optimizing resource allocation for a secure Addis Ababa.
### Metrics Used For Evaluation.
Based on the objectives of the project, the following metrics can be considered for evaluating the success of the project:

1. **Severity Classification Accuracy:** Assess the overall correctness of our model's severity predictions across all categories.

2. **Severity Precision, Recall, and F1-Score:** Evaluate the precision, recall, and F1-score for each severity category to gauge the accuracy of our predictions for different accident levels.

3. **Severity Differentiation (AUC-ROC):** measure our model's ability to distinguish between severity classes, especially for binary scenarios like 'Slight' vs. 'serious' and Fatal.

4. **Confusion Matrix:** Construct a confusion matrix to visualize the number of correct and incorrect predictions for each severity category. This matrix helps in understanding the model's strengths and weaknesses.

These metrics collectively offer a comprehensive assessment of our project's predictive model, focusing on accuracy, precision, recall, differentiation, and robustness to imbalanced data.
### d. Metrics Used For success
Our project will be deemed a success if we achieve the following outcomes based on the defined metrics:

1. **High Severity Classification Accuracy:** A high overall correctness rate in predicting accident severity categories, ensuring that the model reliably categorizes accidents as 'Slight', 'Serious', or 'Fatal'.

2. **Balanced Precision, Recall, and F1-Score:** The precision, recall, and F1-scores for each severity category are well-balanced, indicating that the model's predictions are accurate across various levels of accident severity.

3. **Strong Severity Differentiation (High AUC-ROC):** The model demonstrates a strong ability to distinguish between severity classes, particularly in binary scenarios like 'Slight' vs. 'Serious', as indicated by a high Area Under the ROC curve.

4. **Interpretability through Confusion Matrix:** The confusion matrix provides clear insights into the number of accurate and inaccurate predictions for each severity category. This information helps us understand the model's strengths and areas for improvement.

5. **Generalization and Robustness:** The model performs well on unseen data, indicating that it can generalize effectively to new accident scenarios. It is also robust to imbalanced data, providing accurate predictions even for rare classes.

6. **Positive Stakeholder Feedback:** Key stakeholders, including the Addis Ababa Urban Planning Institute, Emergency Services, and Road Safety Authority, find value in the model's predictions. They can use these insights to inform decisions and enhance safety measures.

7. **Optimized Resource Allocation:** The model contributes to optimized resource allocation by enabling emergency responders to efficiently allocate resources based on predicted severity levels, potentially leading to reduced response times and enhanced emergency services.

8. **Safer Urban Environment:** The model's predictions contribute to a safer urban environment by influencing urban planning decisions, emergency response effectiveness, and road safety initiatives. This is reflected in a reduction of accident severity and improved allocation of safety resources.

By achieving these outcomes, we will have successfully developed a robust and reliable predictive model that effectively addresses the project's objectives, empowers stakeholders with actionable insights, and contributes to the enhancement of road safety and urban well-being in Addis Ababa.
## Data Understanding
Data understanding is a critical step in any data analysis or modeling process. It involves getting familiar with the dataset, its features, and its characteristics. Based on the dataset used, here's a data understanding summary:

<a href="https://www.kaggle.com/datasets/saurabhshahane/road-traffic-accidents">Kaggle Page</a>

**Dataset Overview:**
- Source: Addis Ababa Sub city police department records
- Time Period: Year 2017-2020
- Number of Instances (Rows): 12316
- Number of Features (Columns): 32

**Columns:** (with data type in brackets)
1. 'Time': The time of the accident occurrence. (ordinal)
2. 'Day_of_week': The day of the week when the accident occurred. (norminal)
3. 'Age_band_of_driver': Age group of the driver involved in the accident. (ordinal)
4. 'Sex_of_driver': Gender of the driver. (norminal)
5. 'Educational_level': Educational level of the driver. (ordinal)
6. 'Vehicle_driver_relation': Relationship between the driver and the vehicle. (norminal)
7. 'Driving_experience': Experience level of the driver. (ordinal)
8. 'Type_of_vehicle': Type of vehicle involved in the accident. (norminal)
9. 'Owner_of_vehicle': Owner of the vehicle. (norminal)
10. 'Service_year_of_vehicle': Years of service of the vehicle. (ordinal)
11. 'Defect_of_vehicle': Defect of the vehicle that might have contributed to the accident. (norminal)
12. 'Area_accident_occured': Area where the accident occurred. (norminal)
13. 'Lanes_or_Medians': Information about lanes or medians. (norminal)
14. 'Road_allignment': Alignment of the road. (norminal)
15. 'Types_of_Junction': Type of road junction where the accident occurred. (norminal)
16. 'Road_surface_type': Type of road surface. (norminal)
17. 'Road_surface_conditions': Conditions of the road surface during the accident. (norminal)
18. 'Light_conditions': Lighting conditions during the accident. (ordinal)
19. 'Weather_conditions': Weather conditions during the accident. (norminal)
20. 'Type_of_collision': Type of collision that occurred. (norminal)
21. 'Number_of_vehicles_involved': Number of vehicles involved in the accident. (discrete)
22. 'Number_of_casualties': Number of casualties in the accident. (discrete)
23. 'Vehicle_movement': Movement of the vehicle at the time of the accident. (norminal)
24. 'Casualty_class': Class of the casualty (e.g., driver, passenger, pedestrian). (norminal)
25. 'Sex_of_casualty': Gender of the casualty. (norminal)
26. 'Age_band_of_casualty': Age group of the casualty. (ordinal)
27. 'Casualty_severity': Severity level of the casualty. (ordinal)
28. 'Work_of_casuality': Occupation or work status of the casualty. (norminal)
29. 'Fitness_of_casuality': Fitness status of the casualty. (norminal)
30. 'Pedestrian_movement': Movement of pedestrians involved in the accident. (norminal)
31. 'Cause_of_accident': Probable cause of the accident. (norminal)
32. 'Accident_severity': Severity level of the accident. (ordinal) ~ Target
## Modeling
### Strategy

1. **Create Baseline Model**
    - Develop a baseline classification model to establish initial performance benchmarks.

2. **Explore Advanced Models**
    - Implement the following advanced models:
        1. Model_1: Decision Trees
        2. Model_2: Logistic Regression
        3. Model_3: K-Nearest Neighbors (KNN) Classifier
        4. Model_4: Random Forests

3. **Select Best Model**
    - Evaluate the performance of each advanced model and select the one with the highest accuracy and suitable characteristics. We found the best model to be the random forest model.
    - ![image](https://github.com/MrKipkorir/phasecollaboration/assets/87811071/4a6bef94-bb1d-43da-8a03-57f7af51c334)

![image](https://github.com/MrKipkorir/phasecollaboration/assets/87811071/22c5c92d-5f9e-40b6-b7a3-97a53db7793f)

4. **Hyperparameter Tuning**
    - Utilize GridSearchCV to optimize the hyperparameters of the selected model.
    5. Model_5: Best Model with Hyperparameter Tuning

5. **Feature Selection and Ensemble Methods**
    - Employ feature selection techniques to enhance model efficiency and reduce noise.
    - Explore ensemble methods to combine multiple models for improved predictive power.
    6. Model_6: Ensemble Model
### Conclusion

Our project focused on predicting "Accident_severity" in Addis Ababa, utilizing a range of machine learning algorithms. Through the application of advanced techniques like Logistic Regression, K-Nearest Neighbors, Decision Trees, and Random Forests, we significantly improved our initial accuracy of 0.5.

Key features such as "Day_of_week," "Hour," and "Area_accident_occured" emerged as critical contributors, resulting in comprehensive classification reports with precision, recall, and F1-scores for distinct severity classes.

Model performances exhibited variations: Logistic Regression achieved 0.58 accuracy, K-Nearest Neighbors and Decision Trees reached 0.65 and 0.86 respectively, while the Random Forest model led with an impressive 0.90 accuracy. Further improvements brought the RandomForest classifier to an accuracy of 0.92, and our final model achieved a perfect 1.

Each model showcased unique strengths: Logistic Regression balanced precision and recall, K-Nearest Neighbors highlighted similarity-based learning, Decision Trees revealed transparent decision pathways, and Random Forests effectively managed overfitting concerns.

Our findings hold significant practical implications for Addis Ababa stakeholders. The Urban Planning Institute can optimize traffic management, Emergency Services can allocate resources efficiently, and the Road Safety Authority can target tailored awareness campaigns for safer driving.

In conclusion, our project advances accident severity prediction and delivers actionable insights that resonate with stakeholders, driving efforts for safer roads in Addis Ababa. By combining machine learning with informed decision-making, we move closer to our goal of reducing accidents and enhancing road safety in the city.
### Recommendations to Stakeholders

These tailored recommendations aim to enhance urban planning, emergency response, and road safety efforts in Addis Ababa. Based on thorough model evaluations and utilizing specific features, each stakeholder can make informed decisions to mitigate accident risks and improve overall safety on the roads.
### Addis Ababa Urban Planning Institute:

1. **Day_of_week and Hour Insights:** Analyze accident occurrences based on "Day_of_week" and "Hour" to identify high-risk periods. Plan urban development and traffic management strategies that address peak risk times effectively.

2. **Area_accident_occured and Road_allignment:** Identify accident-prone areas using "Area_accident_occured" and "Road_allignment" features. Implement infrastructure improvements and road realignment in these zones to mitigate risks.

3. **Driving Experience and Educational Level:** Collaborate with driving schools to enhance education programs, focusing on "Driving_experience" and "Educational_level." Promote defensive driving techniques, especially for less experienced or lower-educated drivers.

### Addis Ababa Emergency Services:

1. **Accident_severity and Number of Casualties/Vehicles Involved:** Allocate resources based on "Accident_severity," "Number_of_casualties," and "Number_of_vehicles_involved" predictions. Prioritize emergency responses for incidents with higher predicted severity and more casualties/vehicles.

2. **Type of Vehicle and Owner of Vehicle:** Work with manufacturers and vehicle owners based on "Type_of_vehicle" and "Owner_of_vehicle" insights. Ensure proper maintenance and safety standards for specific vehicle types, contributing to accident prevention.

### Addis Ababa Road Safety Authority:

1. **Weather_conditions, Light_conditions, and Type_of_collision:** Develop safety guidelines and campaigns based on "Weather_conditions," "Light_conditions," and "Type_of_collision." Educate drivers about safe practices during adverse conditions and collision types identified.

2. **Pedestrian Movement and Lanes or Medians:** Enhance pedestrian safety with "Pedestrian_movement" and "Lanes_or_Medians" insights. Design pedestrian-friendly infrastructure and optimize road layouts with appropriate lanes and medians.

3. **Vehicle Driver Relation, Sex of Driver, and Cause of Accident:** Tailor awareness campaigns based on "Vehicle_driver_relation," "Sex_of_driver," and "Cause_of_accident" features. Educate specific demographics about responsible driving behaviors and accident prevention strategies.

These recommendations provide a comprehensive framework for each client to enhance urban planning, emergency response, and road safety efforts in Addis Ababa based on the model evaluations and the specific features they use.
