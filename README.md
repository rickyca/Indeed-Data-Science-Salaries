## Salary Classification and Prediction

The objective of this project is to predict job salaries based on Data Scientist job posts scrapped from Indeed.com. For this, job positions
were obtained from 15 cities from different US states. Three features were used in this analysis: job title, location, and salary.

There are some considerations to take into account:
- Firstly, only about 500 of the jobs obtained contained salary information, limiting our modeling. One way to prevent this is to collect data over a longer period of time or simply combining jobs websites, such as Monster or Linkedin.
- Secondly, each location or state contains a different amount of job postings. In fact, California and New York had the most job postings. In consequence, our results will be biased by these two cities. Even though there are several ways to mitigate this effect, all of them required
more data.
- Lastly, after looking at the job titles obtained, there are a lot of jobs that are not data science. For example, data engineer, research or analyst. Considering that these extra jobs will affect our results I personally felt that it would be interesting to take them into account as this job posts appear when searching for data science.

The model proposed consists of two phases: an initial classifier followed by a salary predictor (regression). After analyzing the data and identifying two main groups based on salaries and titles it was clear that we can split them into two groups. The first one mainly contains data science roles while the second group contained research, analyst, and associate level roles.

In order to train the model using the training data, which is 70 % of the collected data, two categories were created: salaries over 110 thousands and salaries lower than 110 thousands. With this information a Random Regression Classifier model was trained. One thing to have in mind is that this part of the process is crucial, because after classifying new data there will be two different models for each predicted category. If the jobs are misclassified it could result in a higher error in the salary prediction.

The second phase, which consists of two identical models for each category, consist of two regression models. This predicts the final salary.
Both of them were trained independently, by each subgroup in the training data.

After evaluating the test data, there was a performance (R2) of 0.5. This means that the result is at least two times better than a random choice, based on the mean value of salaries.

Considering the limitation in the data used and all the considerations above there was a good overall result in the final prediction of salaries.
The model proposed can be improved significantly by collecting more data, task that can be done in less than two months if we want to keep the same criteria or in less than one week by gathering data from new resources.
