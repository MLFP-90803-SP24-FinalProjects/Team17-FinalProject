# Machine Learning Foundations with Python - 90803
## Spring 2024

### Title
Climate-Driven Housing Price Prediction: Navigating Environmental Displacement in the U.S.

### Presentation Link
This is the link to our presentation on Google Slides: https://docs.google.com/presentation/d/1rO4J3T3Bt6npnWvWx7htCh_njVdzMI45wEdXniRzCTY/edit?usp=sharing<br><br>
A PDF of these slides is included in this repo as well, but we have an animation that only runs on Google Slides. 

### Authors
Quintessa Guengerich, qguenger@andrew.cmu.edu<br>
Jewel Kentilitisca, jkentili@andrew.cmu.edu<br>
Hannah Nguyen, hieuhann@andrew.cmu.edu<br>

### Disclaimer
This project contains research based on open-source data and is solely for academic purposes. The authors recognize the complexity of climate change and its impact on certain communities. The reliability of our results heavily depend on the quality, completeness, and accuracy of the data used in the analysis. That being said, we approached our conclusions for this research with caution on their meanings for these communities and believe ongoing research should be conducted to derive attainable solutions for uplifting communities affected by climate change. We hope to contribute to efforts towards understanding and supporting these communities through uncovering one aspect of this issue. 

### Description of Context
This project predicts housing prices based on data of climate indicators. This is relevant because climate change is reshaping U.S. geography, thus, displacing large communities in areas that experience a variety of extreme climate events and even higher risk of environmental disasters. 

**- Why is this topic relevant?**<br>
Prevalent effects of climate change are influencing the decision on individual's real estate investments. Rising global temperature have a domino effect, causing other climate change events like extreme weather and higher sea levels. This could range from higher temperatures to danageraout, destructive storms with wind damage or higher risks of flooding. As temperatures rise and costs go up, it makes sense that people may be relocating to cooler areas to decrease energy costs and to distance themselves from areas prone to heightened air pollution levels and risks of heat-related illnesses and mortality.
  
**- Who does this topic affect? Where does it happen? When did it happen?**<br>
In areas of rising temperatures, more people are using electricity for air-condition or other cooling methods, putting strain on the electrical grid, raising the prices for these utilities. This is even more densely populated areas, "urban heat island", where increases energy costs (e.g., for air conditioning), air pollution levels, and heat-related illness and mortality.

**- What are your motivations for addressing this topic?**<br>
With friends and family living in these high-risk areas, we are motivated to pursue this topic. We are also interested in exploring the intersectionality between housing and environmental policies and proposing holistic interpretations to a complex problem.

### Ethical Consideration
Our research used open-sourced data to train and test the machine learning algorithms. This means that the quality of our results and conclusions are dependent upon the completeness and accuracy of the data we obtained. We made an effort to frame our findings within the scope of the data and research questions we had so as not to extrapolate beyond our dataset. We also discussed potential next-steps to expand upon our dataset and include more features that would allow for better understanding of the problem at hand. Another ethical consideration is about privacy. Our research involves identifying housing prices by location but at no point did we include specific information that can identify a residence on a map. Our housing price data is averaged by county, as well as our geodata for mapping. 

### Questions to Answer
1. Can we predict real estate purchase price based on climate indicators?
- Target variable: Real estate purchase price
- Task: Regression analysis to predict investment patterns based on historical weather data.

2. Can we classify counties in historically "Warm Temperature", "Moderate Temperature", and "Cold Temperature" States as Not Outliers and Outliers?<br>
Note: By Leveraging linear regression, particularly RANSAC, we initially identified outliers among counties. We seek to expand this classification to regions with similar annual temperature averages.
- Target variable: states that were identified as outliers by RANSAC() = 1 vs states that were not not outliers = 0
- Task: Run classification models to see if we can classify which state is an outlier (corresponds to being historically warm according to our domain knowledge) and which state is not an outlier (not a historicall warm state) based on the features in our climate-housing dataset.

3. Are there any hidden associations between housing prices and average temperature or temperature anomalies that is worth exploring?
- Target variable: None
- Task: Unsupervised learning with the entire dataset then analyze the clusters through visualization.

### Description of the Dataset
We have three main datasets, listed below. All can be downloaded in our team folder. 

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
 
After collecting all the data, we merged them together into all_data.csv. Due to run time problems where extracting a geodataframe into csv takes much more time than performing the merging process, every notebook merged all_data.csv with the 2022 US county shapefile. Everything is further explained in the 'Merging_Data' notebook. Our cleaning notebooks also produced climate_data.csv and homevalues.csv. These datafiles are the cleaned but pre-merged. Our RANSAC model also produced all_data_w_outliers.csv which we used in 'Q2_Classification.ipynb'

### Model Evaluation: How We Interpret Our Models' Performance

**Question #1:** Regression<br>
We performed feature engineering (selection, scaling, etc.) and tested different version of the model until we get the best R2 and MSE. We also tried different alpha levels for Ridge and Lasso and will perform cross-validation. We will be using MSE and R2 as our main metrics because of they are standard metrics for evaluating regression models. We will try different regression models until we find the best model, but for now, we are most interested in the RANSAC regression model because it gives us interesting information about the outliers that we can perform more analyses on with different methods.

**Question #2:** Classification<br>
Before starting, we think it is more harmful to miss labeling an outlier. Given this scenario, since we are trying to look for areas affected by temperature anomalies on housing prices, it would be more harmful in missing labeling an outlier than incorrectly labeling a not outlier as an outlier. Since recall measures the ability of a model to correctly identify all relevant instances (outliers in this case), we would want to reduce the number of false negatives. We would be able to minimize the risk of failing to identify areas affected by temperature anomalies on housing prices. The models that performed that best have been Random Forests Classifier and XGBooster. 
<br>
For Random Forests Classifier: 
- n_estimators: This gives us the number of trees in the forest. Increasing the number of trees could possibly improve the model's ability to capture the complex relationships in the data, and in this case is outliers, so we will be trying different ranges of n_estimators. 
- max_depth: Gives the max depth of each tree so that a deeper tree structure allows the model to capture more intricate patterns in the data. This could aid in distinguishing the outliers from normal data points.
- min_samples_split: These parameters control the minimum number of samples required to split an internal node. So we would want to set higher values for these parameters to help prevent the model from overfitting to noise in the data and so preserving the meaning of the outliers.
- max_features: Looks at the number of features to consider when looking for the best split. Putting bounds on the number of features considered at each split can help prevent the model from focusing too much on features that are irrelevant and  could improve its ability to identify meaningful outliers.
<br>
For XGBooster: 
Parameters we would want to use since XGBooster gives higher accuracy is: 
- scale_pos_weight: since our data is locating outliers, we would want to set scale_pos_weight to a value greater than 1 can give more importance to the minority class (outliers), which in turn would help the model to better capture their patterns
- objective: 'binary:logistic', since we want to detect outliers, we are thinking of using an objective function that penalizes errors differently for outliers and normal instances
- max_depth/min_child_weight: since we want to capture outliers, we want something that can lead to deeper and more complex trees, which may better capture the patterns of outliers<br><br>

**Question 3:** Unsupervised Learning<br>
 We first identified that the dataset is highly correlated so we performed PCA to get the best version of the dataset for unsupervised learning. We used the Davies-Bouldin Index as a scoring metrics for our unsupervised models. We tried using Silhouette Score as a metric, but it resulted in a MemoryError due to the amount of data we have. Davies-Bouldin Index is suitable for dataset where we do not know the ground truth and requires less computational power. It also takes into account in its evaluation both the distance within clusters and distance between clusters. To ensure we have the best unsupervised models, we performed tuning for their hyper-parameters:
 - KMeans: We used the Elbow plot and Calinski-Harabasz plot to find the best number of clusters. We got different results for these plots so we tried KMeans with every values that were recommended. We then picked the value that gave us the best Index.
 - Hierarchical Clustering: We used a dendogram to identify the best number of clusters. We visually assessed the dendogram and chose a number that made sense. We also tried different linkage style to see which style gave us the most balanced clusters.
 - DBSCAN: We very systematically tuned min_samples and epsilon. We first identified a relative good min_samples that are appropriate for our dataset as suggested by literature (2*dimension). Then, we used a Nearest Neighbor plot to identify a good range for epsilon with our chosen min_samples. Finally, we iterature through different min_samples, epsilon combinations and chose the combination that gave us the best index.

### Additional Models
1. RANSAC for Q1 (Regression): RANSAC sequentially fits a line through our data then returns the samples that are outliers. In the context of this problem, we found that the outliers are located in states that have more volatile climate conditions. We can then use these outliers for more analyses.
2. XGBooster for Q2 (Classification): XGBoost uses the gradient boosting decision tree algorithm where it creates new models that predict the residuals or errors of prior models and then added together to make the final prediction. In answering our classification question, it uses county attributes and labeled outlier/inlier status the RANSAC model to distinguish outliers and inliers by building decision trees to minimize errors.
3. DBSCAN for Q3 (Unsupervised): DBSCAN clusters by density and is scalable to big dataset. It views clusters as areas of high density separated by areas of low density and able to form clusters in any shape (as opposed to KMeans that assume our clusters are convex). It is quite popular among clusters with high density like our dataset.

### Running the Project

1. Getting the Data: <br>
In our Drive folder for team17, the minimum you need to download for the models to run are:
- all_data.csv (the cleaned, merged dataset)
- tl_2022_us_county folder (US County shapefiles)
- all_data_w_outliers.csv (a dataset containing outliers, obtained by RANSAC, that is later used in one of the modeling notebooks)<br><br>
The other files are either raw data or pre-merge data:
- climate_data_csv folder: all the raw datasets relating to climate
- top_tier.csv: one of the raw datasets relating to housing
- bottom_tier.csv: one of the raw datasets relating to housing
- Table26-2019-by-Month.xls: one of the raw datasets relating to housing
- homevalues.csv: cleaned but pre-merge dataset for all housing data
- climate_cleaned.csv: cleaned but pre-merge dataset for all climate data

2. Cleaning the Data: <br>
You must have the raw datasets if you decide to run these cleaning notebooks. Please run all cells in the following notebooks in no particular order:
- Mortgage_Data_Cleaning.ipynb
- Housing_Data_Cleaning.ipynb
- Climate_Data_Cleaning.ipynb

3. Merging the Data: <br>
You must have the cleaned but pre-merge datasets if you decide to run this notebook. Please run all cells in "Merging_Data.ipynb".

4. Important Checks before Running the Models:<br>
- Be sure that geospatial shape files are located in "tl_2022_us_county" directory (should be able to unzip from google drive accordingly.)
- All other CSV files should be in the same directory as the Jupyter notebooks.
- **Do not forget to include state_names.py in the same directory as the Jupyter notebooks.**

5. Answering the Questions: <br>
- Question 1: Please refer to "Q1_Regression_Analysis.ipynb", "Q1_RANSAC_Regression.ipynb", and "Q1_Per_County_Regressions.ipynb".
- Question 2: Please refer to  "Q2_Classification.ipynb"
- Question 3: Please refer to "Q3_Clustering.ipynb"

### Team Contract

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

### References
1. https://www.fhfa.gov/DataTools/Downloads/Documents/Historical-Summary-Tables/Table26-2019-by-Month.xls
2. https://files.zillowstatic.com/research/public_csvs/zhvi/County_zhvi_uc_sfrcondo_tier_0.67_1.0_sm_sa_month.csv?t=1709428647
3. https://files.zillowstatic.com/research/public_csvs/zhvi/County_zhvi_uc_sfrcondo_tier_0.0_0.33_sm_sa_month.csv?t=1709428647
4. https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/county/mapping/110/tavg/202301/1/value
5. https://canvas.cmu.edu/courses/38950/assignments/707439 (We referred to the example disclaimer to understand what we should write. We adopted it to our project, but we are citing the disclaimer example as a reference just in case)
6. https://www.migrationpolicy.org/article/climate-migration-101-explainer#:~:text=Over%20time%2C%20a%20bigger%20issue,which%20can%20lead%20to%20migration.

Other coding references are cited in each notebook. 
