# Machine Learning Assignment

In this assignment, you will examine a chosen data set and the associated paper, and then apply Machine Learning to the data using the Weka software. You'll then prepare a presentation about the paper, the data and your Machine Learning experiments.

## Choose your topic 

You have a choice of 5 data sets and Machine Learning tasks:

1. Classifying pottery based on their chemical compositions (https://doi.org/10.3390/su141811214)
2. Estimating the sex of human skulls, based on their measurements (https://doi.org/10.3390/app12189285)
3. Classifying types of Middle Eastern pottery based on measurements (https://hdl.handle.net/1887/3421358)
4. Estimating age of pigs (Sus scrofa) (https://doi.org/10.1016/j.jas.2020.105115)
5. Classifying plant species based on phytolith measurements (https://doi.org/10.1007/s12520-015-0235-6)

To get started, first read the paper linked to your chosen data. In case of the thesis (choice number 3), read sections 1 and 2, and also have a look at table 3.1. 


## Data inspection

Now you know what the task is, it is time to inspect the data. Download the spreadsheet (in CSV format) for your chosen subject below. (use right-click > "save link as..." to download the files)

1. https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/pottery-chemical/chemical-pottery.csv
2. https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/sex-estimation-skulls/sex-estimation.csv
3. https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/pottery-measurements/pottery.csv
4. https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/age-estimation-sus-scrofa/age-estimation.csv
5. https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/plant-phytoliths/phytoliths.csv

Open the .csv file in Excel, OpenOffice Calc, or Google Sheets, and have a look through the data. Pay special attention to the data types: do the columns contain text or numbers? Try and find out which column contains the class or target label, based on what you've read in the article/thesis. This is important as you will need to select the class column later!

## Start the experiments

You have inspected the data, now it's time to import the data into Weka and do some Machine Learning! Follow the following steps:

- Download your chosen data again, but this time in the .arff format that Weka needs:
	- https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/pottery-chemical/chemical-pottery.arff
	- https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/sex-estimation-skulls/sex-estimation.arff
	- https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/pottery-measurements/pottery.arff
	- https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/age-estimation-sus-scrofa/age-estimation.arff
	- https://github.com/alexbrandsen/machine-learning-with-WEKA/raw/main/data/plant-phytoliths/phytoliths.arff
- Download Weka for your operating system (https://waikato.github.io/weka-wiki/downloading_weka/#stable-version)
- Install Weka via the installer you downloaded
- Once it's installed, open Weka
- Click on Explorer
- In Preprocess, click Open File...
- Find the .arff data file you’ve downloaded, select it
- You'll now see the columns from the data in the bottom left. You can click on each column to see descriptive statistics for that variable (min, max, mean, distribution, etc)
- Based on your inspection of the data, decide if you want to remove some columns that are not useful (think of ID numbers, other text information that doesn't help with classifying)
- Once done, click on Classify
- Select More options... > Evaluation metrics... > None, then scroll down and select F-measure, Recall and Precision, then click OK and X
- Click Cross-validation
- Select the class to be predicted by the Machine Learning in the dropdown box on the left
- Click Choose, and select an algorithm that’s not greyed out (reference the slides for common algorithms)
- Click Start
	- If you get an error about string attributes, go back to your data in the Preprocess tab, and remove the column containing text
- Once the algorithm has been trained and evaluated, look at the results on the right 
	- Pay attention to the total F-measure ("Weighted Avg."), this is an indication of how well the algorithm works overall 
	- Also look at the F-measure per class, are some classes easier to predict than others? Why do you think this is?
	- Do you see a pattern in the recall and precision? Is one generally higher than the other? What do you think this means?
- Try multiple algorithms, see if you can find the best one (highest Weighted Avg. F-measure)! Try at least 4 algorithms
- You can also try removing some of the columns by going back to the Preprocess tab. Sometimes more columns means more noise, which can make it harder to predict for the algorithm!

Once you're done experimenting, and think you have found the best performing algorithm, you can start preparing your presentation. 

## Presentation

Presentations should contain the following elements:

- An introduction to the problem (summary of paper/thesis)
- A short description of the data (what is the class, how many classes are there, what type of data is used as features)
- A results table (F1, precision and recall for each class) of the best performing Machine Learning algorithm (you can copy this from Weka)
- A brief explanation of the Machine Learning method you got the best results with (read up on the algorithm on Wikipedia)
- Optional: anything interesting you found during your experiments (think of classes with very high or very low F1, or increasing the F1 by removing columns)
- Summarise your findings. Do you think AI can take over from archaeologists for this task?


Your presentation will be graded on the clarity of the introduction of the problem, how well you describe the data and the results, and how clear your explanation of your chosen algorithm is. There are bonus points to be gained for interesting findings and/or conclusions!
