#Analyze MovieLens data
##Project Description
I set up a standalone single node cluster in Hadoop to utilize YARN and HDFS to perform Apache Hive queries through a CLI application to analyze data from a Movie-lens dataset.

##Technologies Used
 *Hadoop - version 2.7.3.2.6.5.0-292
 *HDFS - version 2.7.3.2.6.5.0-292
 *Hive - version 2.6.5.0-292
 *Git -version 2.32.0.windows.1
##Features
List of features ready and TODOs for future development using this project some query are solved using hiveQL ,following questions are listed below:

1.first 5 entries from movies table
2.number of unique movies
3.summary of ratings data
4.minimum rating given to a movie
5.maximum rating given to a movie
6.is any row null in tags
7.number of unique tags
7.drop null rows from tags and create another table of the resulting rows
8.filtering to get the list of drama movies
9.total number of drama movies
10.filtering to get the list of comedy movies
11.total no. of comedy movies
12.search movie id by tag search
13.displays first 5 data from ratings table
14.merging two tables movies and ratings into a new table without the "timestamp" column from the ratings table.
15.display high rated movies (rating > 4)
16.display low rated movies (rating < 4)
17.total number of unique movie genres
18.top 25 most rated movies
19.slicing out columns to display only title and genres columns from movies table
20.extract year from title of the movie
21.count how many times each of genres occur
22.Which movie received the highest number of ratings?

##Getting Started
To start this project user need to install sandbox-Hortonworks in virtual machine.After installing the VM start the VM then put the following command in Git bash then connect to VM using SSH command "ssh maria_dev@sandbox-hdp.hortonworks.com -p 2222" after this you need to put the password the default password for USER maria_dev is "maria_dev"

Performing the above action you are enter to VM CLI then do the following command which are listed below for the project.

*Create a folder in local VM using command "mkdir folder_name"
*In this folder clone the git repository from where we pull the dataset using command "git clone 'git repository link' "
*All dataet are in a zip file we have to unzip it using command "unzip file_name" (N.B: if you are unzip in the current file ) .
*After unzip all the file create a folder in hdfs using command which is little bit difference before we tried while creating folder is "hdfs dfs -mkdir folder_name" (By *default this folder created in the path user/maria_dev/ ) and copy all file to the hdfs folder by ""hdfs dfs -put file-name /user/maria_dev/folder_name".
*To open HiveQL terminal we have have to give command "Hive".
*Before performing all the above action try to check whether your Ambari which is management platform for hadoop started all services or not.
*In hive terminal ,check database and if not create one and use the database using following command and after creating database create tables and load data from the folder in *hdfs to the respected table and perform analysis using the query which are mention the txt file "project_1_command.txt"

###For creating database
create database project1; (#"project1" is the database name here)

###For work in the database
use project1;

###create table
CREATE TABLE movies (movieId int, title string, genres varchar(200))
row format delimited
fields terminated by ',';
load data into table
LOAD DATA INPATH '/user/maria_dev/project_1/movies.csv'
INTO TABLE project1.movies;
The above Query are for creating table and load data in it,after loading data to the table all data from the hdfs folder are automatically removed i.e they are now loaded in the respective tables.

###Usage
Using this project any one can perform analysis with the movielens dataset
