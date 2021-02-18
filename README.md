# apache_beam_python-WordCount
Apache beam python wordcount transformation
<img src="https://avatars.githubusercontent.com/u/60015515?s=400&u=a691ffb3d3f0d5b6668835340aa29ca8599d7667&v=4" align="right"
     alt="Size Limit logo by Anton Lovchikov" width="110" height="120">
     
# Pooja Gundu [![](https://img.shields.io/badge/Github-GUNDUPOOJA)](https://github.com/GUNDUPOOJA)
## Sub-topic : WordCount
- I have worked on "Word Count" for the file 'superbowl-ads.csv' This file contains data about all advertisements shown during the Super Bowl(most watched US Program) across the years from 1967 to 2020.
* The dataset, I have choosen is Kaggle. Here is the link [superbowl-ads.csv](https://www.kaggle.com/prondeau/superbowlads)
* I have choosen the Google colaboratory to run the code.
- [Pooja's Google Colab Notebook on wordcount Transformation](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/superbowl_ads.ipynb)
- Demonstration Video: []()
- [source repo](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount)

## Apache-beam 
- Apache Beam is an open source unified programming model to define and execute data processing pipelines, including ETL, batch and stream (continuous) processing.
- Original author: GOOGLE, released in the year 2016.
- written in Java, Python, Go languages.
- ETL allows businesses to gather data from multiple sources and consolidate it into a single, centralized location

## Data pipelines:
- consolidating data from all your disparate sources into one common destination, enable quick data analysis for business insights.
- They also ensure consistent data quality, which is absolutely crucial for reliable business insights.

## Batch pipeline: 
- The type of pipeline used to process the data in batches.

## Streaming Data pipelines:
- These pipelines handles millions of events at scale in real time.

## Google Colab
- It is a collaboration tool similar to Jupyter notebook.
- Everything is pre-installed, no need to explicitly install anything.
- Sign in to Google colab account and after writing, testing the code save the file in Github or in local machine.

## Prerequisites
- Apache Beam 
- Python
- Google Colab
- Google drive account

## Installation steps 
- Check the versions on your machine using commands 
``` 
python --version
```
```
pip --version
```
## Process and the Commands used to do word count transformation.
- Create a google colab account and open a new notebook, rename it as you required.
- First, install the apache-beam using the below command
``` 
python -m pip install apache-beam
```
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/apache-install%20command.PNG)

## To install extra dependencies use the below command
``` 
pip install apache-beam[gcp,aws,test,docs]
```
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/beam-dependencies.PNG)

- For more information, click this [link](https://beam.apache.org/get-started/quickstart-py/)

- Program that performs the word count operation
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/wordcount-logic.PNG)

- output of the program
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/outputimage.PNG)
- The command that lists all the files
```
! ls
```
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/listitems.PNG)
- First upload your .csv file to your google drive account. The email used should be same for both google drive and google Colab accounts.
- To Import the .csv file run the below commands otherwise you will get file not found error because it is not imported into google colab.
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/fileimport.PNG)
```
# Code to read csv file into colaboratory:
!pip install -U -q PyDrive
from pydrive.auth import GoogleAuth
from pydrive.drive import GoogleDrive
from google.colab import auth
from oauth2client.client import GoogleCredentials
```
```
# Autheticate E-Mail ID
auth.authenticate_user()
gauth = GoogleAuth()
gauth.credentials = GoogleCredentials.get_application_default()
drive = GoogleDrive(gauth)
```

- To get the id of the file, right-click on the file in google drive account, select share link option, then copy the link.
- Remove the part that contains https://
- keep only the id part.

```
# Get File from Drive using file-ID
# Get the file
downloaded = drive.CreateFile({'id':'1b73yN7MjGytqSP5wimYAQmtByOvGGe8Y'}) # replace the id with id of file you want to access
downloaded.GetContentFile('superbowl-ads.csv') 
```

- Command to add the result to a output file
```
!cat output.txt-00000-of-00001 # output file
```
![](https://github.com/GUNDUPOOJA/apache_beam_python-wordcount/blob/main/outputimage.PNG)

## References 
- [Kaggle](https://www.kaggle.com/)
- [Apache-beam](https://colab.research.google.com/github/apache/beam/blob/master/examples/notebooks/get-started/try-apache-beam-py.ipynb)
- [Youtube Video shows how to import files to google colab](https://www.youtube.com/watch?v=oqMImCeXi6o)





