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
Whatsapp and carrier pigeon across the park. Max response time of 2 days, preferred within 4 hrs.


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
In areas of rising temeratures, more people are using electricity for air-condition or other cooling methods, putting strain on the electrical grid, raising the prices for these utilities. This is even more densely populated areas, "urban heat island", where increases energy costs (e.g., for air conditioning), air pollution levels, and heat-related illness and mortality.

**- What are your motivations for addressing this topic?**<br>
With friends and family living in these high-risk areas, we are motivated to pursue this topic. We are also interested in exploring the intersectionality between housing and environmental policies and proposing holistic interpretations to a complex problem.

### Variable Description
A brief description of the dataset/s you chose (e.g., number of variables, year, etc). 

- Mortgage rates data: https://www.fhfa.gov/DataTools/Downloads/Documents/Historical-Summary-Tables/Table26-2019-by-Month.xls
	- Include an exact link to the dataset (we should be able to download your data directly from this link)
	- DO NOT  include the dataset in your repo! Please put it in your .gitignore, that way you can use the dataset in your local repos but it will not be reflected into your GitHub.
	- Describe the format your data comes in
	- Describe any relevant metadata
	- List the variables (at a high level)

- Housing Data: https://files.zillowstatic.com/research/public_csvs/zhvi/County_zhvi_uc_sfrcondo_tier_0.67_1.0_sm_sa_month.csv?t=1709428647
                https://files.zillowstatic.com/research/public_csvs/zhvi/County_zhvi_uc_sfrcondo_tier_0.0_0.33_sm_sa_month.csv?t=1709428647
Note: We downloaded several different types of data, but I have it commented out of the jupyter notebook because we are ultimtely NOT going to use it after exploring it.
	- Include an exact link to the dataset (we should be able to download your data directly from this link)
	- DO NOT  include the dataset in your repo! Please put it in your .gitignore, that way you can use the dataset in your local repos but it will not be reflected into your GitHub.
	- Describe the format your data comes in
	- Describe any relevant metadata
	- List the variables (at a high level)
- Climate Data: https://drive.google.com/file/d/174KqWkZTk-vSsGW5gtADxE8OU7L0v8g9/view?usp=drive_link
Note: We scraped this data from this website (https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/county/mapping/110/tavg/202301/1/value).
The code for scraping the data is in the climate_data_gathering branch if you would like to run it. It takes about 15 minutes to run.
	- Include an exact link to the dataset (we should be able to download your data directly from this link)
	- DO NOT  include the dataset in your repo! Please put it in your .gitignore, that way you can use the dataset in your local repos but it will not be reflected into your GitHub.
	- Describe the format your data comes in
	- Describe any relevant metadata
	- List the variables (at a high level)


### Questions to Answer

1. How does the frequency and severity of climate indicators correlate with real estate investment patterns in different regions?
- Target variable: Real estate investment volume and value in specific regions in the United States.
- Task: Regression analysis to predict investment patterns based on historical weather data.

2. What is the relationship between rising temperatures and changes in property prices in urban heat island areas?
- Target variable: Property prices or property value indices in urban heat island areas in the United States?
- Task: Correlation analysis to determine the impact of rising temperatures on property prices.

3. How do changes in temperature and precipitation levels correlate with changes in housing market characteristics, such as listing pricing trends, market duration, and inventory levels?
- Target variable: Housing market indicators (listing prices, how long houses are on the market, inventory levels).
- Task: Time-series analysis to examine the impact of weather patterns on housing market dynamics.


### Running the Project

In this section, you can include instructions on how to run your project. Think of them as steps. Include which notebook to run first and what each notebook contains. 
