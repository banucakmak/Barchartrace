# Barchartrace


Welcome to my repository on bar chart races! Here you will find a collection of codes that I have applied while learning from my bootcamp teacher about the process of creating dynamic animations. These codes are focused on creating simple and easy-to-use bar chart races, and are suitable for a wide range of applications. You will find that the codes are simple and easy to understand, making them a great starting point for anyone who wants to learn how to create bar chart races. The repository includes a sample dataset to help you get started with creating your own bar chart races. I hope that these codes will be useful for anyone who is interested in learning about this topic and creating similar animations. Thanks for visiting and happy coding!
Note: Suggesting you to run these on googlecollab 

--------------------------------
### installing the necessary packages

!pip install ffmpeg  

(a command-line tool that can be used to convert multimedia files between different formats. It is commonly used in conjunction with bar chart races to create animations.)

!pip install bar_chart_race 

(a package that allows you to create bar chart races in Python. It is built on top of the popular data visualization library, matplotlib. It makes it easy to create bar chart races by providing a simple and intuitive API for generating the animations.)

------------
import pandas as pd

df=pd.read_csv("corona_dat.csv") 
### A dataset about corona virus status of the countries.

df.head()
![image](https://user-images.githubusercontent.com/122751581/215353454-8829fef7-bf66-418e-b1f1-ecd85091095d.png)

### Selecting the countries to include the race

df2=df[['date','China','Italy','Spain','Brazil','United Kingdom','US','France','Turkey']]

---------------
### To set index of the dataframe to the "date" column to be able to do time based operations on the data as we can use the column to filter and sort the data.

df2.set_index('date',inplace=True)

------------
### Adding up the previous value in the cumulative sum with the current element.

total=df2.cumsum(axis=0) 

------------
### python library for creating  animated bar chart races.

import bar_chart_race as bcr

-------------

### the main code

bcr.bar_chart_race(total,filename="covid.mp4",figsize=(8,5),title="Barchart")

from IPython.display import HTML 
from base64 import b64encode
mp4 = open('covid.mp4','rb').read()
data_url = "data:video/mp4;base64," + b64encode(mp4).decode()
HTML(""" 
<video width=400 controls>
      <source src = "%s" type = "video/mp4">
</video>
""" % data_url)


https://user-images.githubusercontent.com/122751581/215354731-b724ef06-d9bf-4669-8b5f-33f39ac13541.mp4

If you cannot play the video, check the shots!

![image](https://user-images.githubusercontent.com/122751581/215354807-c7cb7a38-0846-473b-8733-3176d6abf960.png)

![image](https://user-images.githubusercontent.com/122751581/215354822-a68892ac-c59c-4c32-bfec-090927d97c65.png)

![image](https://user-images.githubusercontent.com/122751581/215354833-5892a8a9-87d0-4b8e-bfab-dc34137edc9d.png)






