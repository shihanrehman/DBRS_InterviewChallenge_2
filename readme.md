                                      Instructions to Run Application

https://colab.research.google.com/drive/1PGbI4Pj-NoGcD0J6ycZS74_IvOhoVuZq
Click on the Link -> You may have to sign-in with a gmail account if not signed in already.

Colaboraty should open, click Runtime -> Run All

Allow 30 seconds for all downloads and scripts to run -> Project should be running

                                   Instructions to Run Application on Docker-Compose
                           (Assuming that Docker is already installed on a Linux type OS)

Download zip file from here: https://www.dropbox.com/s/92fwq06m974vpxp/docker.zip?dl=0 and unzip to folder in directory, which should default to 'Docker', if not paste the contents of the zip file into a folder named "Docker" or whatever you want.

CD into the 'Docker' folder on terminal or whatever folder you created in step 1)

Edit the docker-compose file, under 'volumes', change the working directory before the ":", specify locally on your computer - can be any path, where to map the current working directory to for your Jupyter projects.

On terminal, once you are cd'd into the folder with all the docker files inside it, type -> sudo docker-compose up (Wait 5 minutes for the images to be downloaded from docker hub and copy the auth token from terminal once docker-compose finishes execution)

Type localhost:8888 on the browser - login to Jupyter with the auth token from step 4- the working directory specified in Step 3 should show up in Jupyter, load the pandas project into Jupyter, with file extension .ipynmb

Click Cell -> Run All

Close docker with Control + C on keyboard, and type docker-compose up if you want to bring it back up again.

                       Architecture and Assumptions about Design and technology tradeoffs

-Google Colaboratory running Jupyter Notebook -> Host the application -Numpy and Pandas -> Python Analytics libraries -Matplotlib -> Display a couple graphs (It was not required, but I decided to use it for aesthetic purposes)

I decided to use Google Colaboratory instead of Docker-Compose as suggested in the challenge.

Docker is great, but for this project, I was very limited to what I could do with docker and 'infrastructure as code'- what docker shines in - no databases, no ports, etc.. - only a single python file. Getting the application up and running quickly was also highly prioritized - so I wanted to keep execution as simple as possible. Quote - "Please consider the fact that we have to get onboarded with your project so adding good documentation for us to follow to set it up is nice to have."

Aditionally, anyone from anywhere around the world with an internet connection - even with no programing knowledge, can get the application up and running in less than a minute with just a couple mouse clicks - no need to even type or use the keyboard!

To get the project up and running with docker, one would have to have an OS built on top of a linux kernal - even with a linux system, Docker has to be downloaded & installed, images have to be downloaded, and commands need to be executed via command line to run the containers - even to shut down the containers! Docker is great for microservices and deploying them - perhaps, an application built with different databases and programming languages all running independently of one another on connected ports all defined via a docker-compose yaml file, making it possibile to update one part without having to the update the other part.

With efficieny in mind, and this project being very data-science focused, I am also guessing that a data scienctist - someone who may not be familiar with docker and infrastructure code, may also want to have a look at it with the least possible effort.

Google Colaboratory has an option where you can create tabbed menus, similar to a tabbed jorurnal/phonebook, making it easy to separate the code into sections by topic. This makes visual presentation and reporting much more appealing.

I tried to keep my code as minimal and short as possible. However, I did write some extra code - only to generate graphs and do some data validation (i.e validate that the records loaded were from 2017), but nothing more than what was needed for other than those specific purposes.

Everything is setup on one Jupyter Notebook running on the cloud.

                                                    Project Instructions 

All tasks below completed.

-Consider only the 10 most common overall complaint types. For each borough, how many of each of those 10 types were there in 2017?

-Consider only the 10 most common overall complaint types. For the 10 most populous zip codes, how many of each of those 10 types were there in 2017?

-Considering all complaint types. Which boroughs are the biggest "complainers" relative to the size of the population in 2017? Meaning, calculate a complaint-index that adjusts for population of the borough.

                                                      Data Cleansing

I took into account funny characters found in the data, particular in the zip codes colum, as well as a few others.

                                                      Data Sources  

I was able to source the data from here, https://dev.socrata.com/foundry/data.cityofnewyork.us/fhrw-4uyv - on the site, I was able to filter data for 2017 and export it to CSV. The CSV file, being about 1.2 GB in sized, was downloaded, zipped to 100MB, and stored in dropbox. The application downloads the data set and unzips it upon execution.

I was able to souce the population by zip code data from here: https://blog.splitwise.com/2013/09/18/the-2010-us-census-population-by-zip-code-totally-free/. The CSV file is in the kilobytes, so it was stored into dropbox. The application downloads is upon execution.
