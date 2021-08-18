# Big-Data-Python-Project-2 
###### by Hemanth Ghosh

An analysis on **RAWG API**.

**RAWG** is the largest **Video Game Database** and game discovery service with **500,000+** games data.



## Tech Stack


* **Apache Spark [3.1.2]** 
Apache Spark is an open source unified analytics engine for large scale data
processing Spark provides an interface for programming entire clusters with implicit data parallelism
and fault tolerance

* **Python [3.8]** 
Python is an interpreted high level general purpose programming language
Python's design philosophy emphasizes code readability with its notable use of significant
indentation

* **PySpark [3.1.2]** 
PySpark is an interface for Apache Spark in Python It not only allows you to
write Spark applications using Python APIs, but also provides the PySpark shell for interactively
analyzing your data in a distributed environment

* **Spark SQL** 
Spark SQL is a Spark module for structured data processing It provides a programming
abstraction called Data Frames and can also act as a distributed SQL query engine It enables
unmodified Hadoop Hive queries to run up to 100 x faster on existing deployments and data

* **Git /GitHub** 
It is a provider of Internet hosting for software development and version control
using Git It offers the distributed version control and source code management functionality of Git

## Data Summary

### Content

Each row contains information about one game. There are several columns that have multiple values like platforms, genres, … In those cases, values are separated by double pipes ||.

#### Column definitions:

* id: An unique ID identifying this Game in RAWG Database
* slug: An unique slug identifying this Game in RAWG Database
* name: Name of the game
* metacritic: Rating of the game on Metacritic
* released: The date the game was released
* tba: To be announced state
* updated: The date the game was last updated
* website: Game Website
* rating: Rating rated by RAWG user
* rating_top: Maximum rating
* playtime: Hours needed to complete the game
* achievements_count: Number of achievements in game
* ratings_count: Number of RAWG users who rated the game
* suggestions_count: Number of RAWG users who suggested the game
* game_series_count: Number of games in the series
* reviews_count: Number of RAWG users who reviewed the game
* platforms: Platforms game was released on. Separated by ||
* developers: Game developers. Separated by ||
* genres: Game genres. Separated by ||
* publishers: Game publishers. Separated by ||
* esrb_rating: ESRB ratings
* added_status_yet: Number of RAWG users had the game as "Not played"
* added_status_owned: Number of RAWG users had the game as "Owned"
* added_status_beaten: Number of RAWG users had the game as "Completed"
* added_status_toplay: Number of RAWG users had the game as "To play"
* added_status_dropped: Number of RAWG users had the game as "Played but not beaten"
* added_status_playing: Number of RAWG users had the game as "Playing"

## Problem Statements
  1. Which is the top most rated games accross all platform.
  2. Which game developer has released the most number of games.
  3. Which game genres has most games.
  4. Number of games released per year 
  5. Games with longest updation time

## DataSet Used

   [RAWG Dataset Document](https://api.rawg.io/docs/)
   
   [RAWG Dataset](https://www.kaggle.com/jummyegg/rawg-game-dataset)
