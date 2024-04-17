[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/nT4M_vAo)
# Sprint 2 - 90803
### Machine Learning Foundations with Python
#### Spring 2024

---

> Modify here: 

For this Lab, you will need to do the following:

1. Git clone your repo to your local machine (look back at Lab 1 if you have any doubts), using the SSH connection.
2. Open the `Sprint2_S24_TeamName` jupyter notebook and work through it.
3. It is advisable to work on different branches and, in the end, merge your branches to `main`.
4. Periodically go back to the terminal to commit your changes to your Jupyter Notebook. Do not wait until the end; make sure to commit for at least every question in the notebook. Remember that doing a commit involves:
	-  Making changes to your jupyter notebook
	-  Adding changes to your staging area (`git add`)
	-  Committing, with a descriptive message of the task you are committing (`git commit -m "descriptive message"`).
	-  Add a gitignore `git add .gitignore` - for the files you want the commit to ignore. For example, in MacOS you might want to ignore `.DS_Store`. Add this to your gitignore `echo .DS_Store >> .gitignore`. Other files that you might want to include here are `ipynb_checkpoints/*`.
	-  Here are some links if you want to read more on [ipynb checkpoints](https://stackoverflow.com/questions/46421663/what-are-jupyter-notebook-checkpoint-files-for) or how to [gitignore](https://stackoverflow.com/questions/35916658/how-to-git-ignore-ipython-notebook-checkpoints-anywhere-in-repository) them.
5. When you are ready to push back to your GitHub remote repo, make sure to:
	- Have any branches merged into `main`
	- `git push origin main`
	- Have your passphrase at hand
	- After the first push, remember to always `git pull` before working on your local repo (to make sure you're up to date) and then `git push` when you are ready to push changes back to your remote repo.



## Notes on this Sprint - To Modify
- Please follow the instructions provided in the videos (CANVAS)
- Once you are done, please answer the questions below. Make sure you have discussed and come to a consensus when addressing the following questions.

> Modify here: 

**1. List the names of all your teammates:**
Quintessa Guengerich, Yoko Kentilitisca, Hannah Nguyen

**2. Agree as a team, what branching strategy do you plan to use in your final projects? Justify your choices**
We are going to do GitFlow development because that is what we are used to in previous projects. We prefer having a develop branch and several feature/chore branches.

**3.Communication: Outline how the team will communicate — including frequency and methods (e.g., email, WhatsApp, team meetings).  What is the maximum expected response time?**
We will communicate via WhatsApp. Max response time of 2 days, preferred within 4 hrs. If we have trouble, we will pull our TA and/or Prof GS into the loop.


**4. Decision-Making: How will decisions be made in this team? How will you stay on track? Do you plan on having meetings or any strategies for working through your final project**
We will discuss primarily in Whatsapp. We will have weekly meetings at Tessa's house.


**5. As with any team project there is always the possibility of conflict arising, if it does in the future, how will you resolve differences? List at least two strategies**
First, we will discuss amongst each other. We are close enough to be able to professionally "call out" each other, and we live nearby. Second, we are available to help each other out if we need to help pick up others' slack.

**6.Commitments: How will you handle different levels of participation and commitment? What process will you follow if someone does not live up to his/her/their responsibilities? (3-5 sentences)**
There is an understanding that everyone is on different levels of their coding experiences. So, by being able to be an open and communicative group, we can all learn from each other and build off of each other's strengths #strengthincollaboration. There is no need to be ashamed when we are all learning, it's best to have weekly check-ups with each other. 


**7.Diversity: How will you accommodate different learning and working styles? Talk about your own styles and schedules for working and come to an agreement (3-6 sentences)**
We think since we all come from different learning, cultural, and social styles, we believe that as a team it makes our need for communication even more important. Everyone has different lives, so we have committed to weekly updates on our project via Whatsapp and when the Sprints are due we will make sure to schedule an in-person meeting with each other the week before to make sure there's enough time to get the project done. We are all flexible and the convenience of us living so close to one another allows us to get the work done efficiently. 


## Sprint 3


### Title
Climate-Driven Housing Price Prediction: Navigating Environmental Displacement in the U.S.

### Authors
Quintessa Guengerich, qguenger@andrew.cmu.edu
Jewel Kentilitisca, jkentili@andrew.cmu.edu
Hannah Nguyen, hieuhann@andrew.cmu.edu

### Brief Description / Context

This project predicts housing prices based on data of climate indicators. This is relevant because climate change is reshaping U.S. geography, thus, displacing large communities in areas that experience a variety of extreme climate events and even higher risk of environmental disasters. 

**- Why is this topic relevant?**<br>
Prevalent effects of climate change are influencing the decision on individual's real estate investments. Rising global temperature have a domino effect, causing other climate change events like extreme weather and higher sea levels. This could range from higher temperatures to danageraout, destructive storms with wind damage or higher risks of flooding. As temperatures rise and costs go up, it makes sense that people may be relocating to cooler areas to decrease energy costs and to distance themselves from areas prone to heightened air pollution levels and risks of heat-related illnesses and mortality.
  
**- Who does this topic affect? Where does it happen? When did it happen?**<br>
In areas of rising temperatures, more people are using electricity for air-condition or other cooling methods, putting strain on the electrical grid, raising the prices for these utilities. This is even more densely populated areas, "urban heat island", where increases energy costs (e.g., for air conditioning), air pollution levels, and heat-related illness and mortality.

**- What are your motivations for addressing this topic?**<br>
With friends and family living in these high-risk areas, we are motivated to pursue this topic. We are also interested in exploring the intersectionality between housing and environmental policies and proposing holistic interpretations to a complex problem.


### Variable Description
We have three main datasets, listed below. All can be downloaded from this Google Drive link: https://drive.google.com/drive/u/1/folders/1zrZRrxCLTGlC9bDl9DJXIw5U_EXbJO7h

- Mortgage rates from 1990 to 2019: 
  + Link: https://www.fhfa.gov/DataTools/Downloads/Documents/Historical-Summary-Tables/Table26-2019-by-Month.xls
  + High-level description: Fixed-rates for conventional single family mortgages obtained from the Federal Housing Finance Agency
  + Format: Excel (.xls) file.
  + Variables: year from 1990 to 2019, month from 1 to 12, contract interest rate (we dropped this column in the cleaning notebook as it is not relevant to our analysis), intial fees and charges, effective rates, term to maturity, loan amount, purchase price, loan-to-price ratio, share of total market.

- Housing Data:
  + Links:
    1. https://files.zillowstatic.com/research/public_csvs/zhvi/County_zhvi_uc_sfrcondo_tier_0.67_1.0_sm_sa_month.csv?t=1709428647 (renamed "top_tier.csv" after downloaded)
    2. https://files.zillowstatic.com/research/public_csvs/zhvi/County_zhvi_uc_sfrcondo_tier_0.0_0.33_sm_sa_month.csv?t=1709428647 (renamed "bottom_tier.csv" after downloaded)
  + High-level description: Monthly average home values from 2000 to 2023 by counties in the U.S. obtained from Zillow.
  + Format: csv files
  + Variables: County information (name, state, id, size ranking, metro, FIPS) and average home values by date (last day of every month from 2000 to 2023).  

- Climate Data:
  + We scraped this data from this [website](https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/county/mapping/110/tavg/202301/1/value). 
  + High-level description: Monthly average temperatures by counties in the U.S. from 2000 to 2023 obtained from the National Oceanic and Atmospheric Administration.
  + Format: csv files
  + Variables: Each csv file contains county information (id, name, state) and average temperatures for a specific month. All files were combined and read into a dataframe of monthly temperature in the cleaning notebook.

### Questions to Answer

1. Can we predict real estate purchase price based on climate indicators?
- Target variable: Real estate purchase price
- Task: Regression analysis to predict investment patterns based on historical weather data.

2. Can counties in states with historically different temperature ranges be classified as outliers or not outliers?<br>
Note: By Leveraging linear regression, particularly RANSAC, we initially identified outliers among counties. We seek to expand this classification to regions with similar annual temperature averages.
- Target variable:the classification of counties as outliers or not outliers. We categorized regions into Warm, Moderate, and Cold groups and will assess outliers within each region separately. Outliers = 1, Not outliers = 0
- Task: Our objective is to investigate whether high temperature anomalies are associated with property price decreases or no increase or vice versa in counties labeled as outliers or if temperature anomalies affected purchase price at any capacity. 

3. Are there any hiddeen structures or associations between housing prices and average temperature that is worth exploring?
- Target variable: None
- Task: Unsupervised learning to uncover hidden patterns in the dataset that are valuable for classification/grouping.

### Model Evaluation

Question #1: Regression<br>
We performed feature engineering (selection, scaling, etc.) and tested different version of the model until we get the best R2 and MSE. We also tried different alpha levels for Ridge and Lasso and will perform cross-validation. We will be using MSE and R2 as our main metrics because of they are standard metrics for evaluating regression models. We will try different regression models until we find the best model, but for now, we are most interested in the RANSAC regression model because it gives us interesting information about the outliers that we can perform more analyses on with different methods.

Question #2: Classification<br>
Before starting, we think it is more harmful to miss labeling an outlier. Given this scenario, since we are trying to look for areas affected by temperature anomalies on housing prices, it would be more harmful in missing labeling an outlier than incorrectly labeling a not outlier as an outlier. Since recall measures the ability of a model to correctly identify all relevant instances (outliers in this case), we would want to reduce the number of false negatives. We would be able to minimize the risk of failing to identify areas affected by temperature anomalies on housing prices. The models that performed that best have been Random Forests Classifier and XGBooster. 
<br>
For Random Forests Classifier: 
-n_estimators: This gives us the number of trees in the forest. Increasing the number of trees could possibly improve the model's ability to capture the complex relationships in the data, and in this case is outliers, so we will be trying different ranges of n_estimators. 
-max_depth: Gives the max depth of each tree so that a deeper tree structure allows the model to capture more intricate patterns in the data. This could aid in distinguishing the outliers from normal data points.
-min_samples_split: These parameters control the minimum number of samples required to split an internal node. So we would want to set higher values for these parameters to help prevent the model from overfitting to noise in the data and so preserving the meaning of the outliers.
-max_features: Looks at the number of features to consider when looking for the best split. Putting bounds on the number of features considered at each split can help prevent the model from focusing too much on features that are irrelevant and  could improve its ability to identify meaningful outliers.
<br>
For XGBooster:
Parameters we would want to use since XGBooster gives higher accuracy is: 
-scale_pos_weight: since our data is locating outliers, we would want to set scale_pos_weight to a value greater than 1 can give more importance to the minority class (outliers), which in turn would help the model to better capture their patterns
-objective: 'binary:logistic', since we want to detect outliers, we are thinking of using an objective function that penalizes errors differently for outliers and normal instances
-max_depth/min_child_weight: since we want to capture outliers, we want something that can lead to deeper and more complex trees, which may better capture the patterns of outliers


Question #3: Unsupervised Learning<br>
The patterns learned from unsupervised learning might inform our next steps with this dataset, whether it is to characterize the clusters or put them through a classfication model. We will also be using the Davies-Bouldin Index as a scoring metrics for our unsupervised models. We tried using Silhouette Score as my metric but the program cannot calculate this score with the amount of data we have. When trying to calculate the Silhouette Score for a default KMeans model with the PCA-transformed dataframe, we had to intervene at 52 minutes of runtime. For Davies-Bouldin, it took 8.3 seconds to run the same model.


### Ethical Consideration
The ethical consideration of our project is to map out counties that have been largely affected by temperature anomalies and to see if housing prices changed based extreme weather events (like heat). Based on climate studies, global warming is likely to reach 1.5°C between 2030 and 2052 if it continues to increase at the current rate. Therefore, it’s important to gather a better understanding of how temperature affects individual’s ability to buy a home or their hesitancy in buying a home in an area with extreme temperatures. This suggest that people are factoring in how climate risk affects their housing choices, which ultimately influences the housing market. Additionally, we aim to uncover any underlying trends that may not have been captured in the data yet, given the substantial temperature fluctuations, especially during the summer months, which have impacted regions worldwide. It can inform both homebuyers, homeowners, and policy makers on how climate could affect the already housing crisis happening in the United States. 

### Additional Models
1. RANSAC for Q1 (Regression): RANSAC sequentially fits a line through our data then returns the samples that are outliers. In the context of this problem, we found that the outliers are located in states that have more volatile climate conditions. We can then use these outliers for more analyses.
2. XGBooster for Q2 (Classification): 
3. OPTICS for Q3 (Unsupervised): Optics is simply another clustering model that can handle large datasets. We want to see if another distance-based clustering method aside from KMeans might give us better clusters.  

### Running the Project

1. Getting the Data: <br>
Please download all the files here: https://drive.google.com/drive/u/1/folders/1zrZRrxCLTGlC9bDl9DJXIw5U_EXbJO7h

2. Cleaning the Data: <br>
Please run all cells in the following notebooks in no particular order:
- Mortgage_Data_Cleaning.ipynb
- Housing_Data_Cleaning.ipynb
- Climate_Data_Cleaning.ipynb

3. Merging the Data: <br>
Please run all cells in "Merging_Data.ipynb".

4. Answering the Questions: <br>
- Question 1: Please run "Q1_Regression_Analysis.ipynb"
- Question 2: Please run "Q2_Classification.ipynb"
- Question 3: Please run "Q3_Clustering.ipynb"
