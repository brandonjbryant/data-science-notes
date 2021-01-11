Easley
Data Science
Stream
Classwork
People
Easley
Data Science
Upcoming
Woohoo, no work due soon!
View all

Announce something to your class

Announcement: ""Now We Know" Review Content"
Ryan Orsinger
Created 10:47 AM10:47 AM
"Now We Know" Review Content

now_we_know_content.md
Text

Material: "Starting Git Repos on GitHub First"
Ryan Orsinger posted a new material: Starting Git Repos on GitHub First
Created Dec 14, 2020Dec 14, 2020

Announcement: "https://www.youtube.com/watch?v=unsc7Yu…"
Ryan Orsinger
Created Dec 14, 2020Dec 14, 2020
https://www.youtube.com/watch?v=unsc7Yutct0 is the video tutorial to “start the repo on GitHub first” approach. By creating the repo on GitHub then cloning it, you avoid the need to do any "git init". You also avoid the need to "connect the remote", so you can push your code by running "git push" once you have commits :)

Assignment: "Fundamentals Quiz"
Ryan Orsinger posted a new assignment: Fundamentals Quiz
Created Dec 10, 2020Dec 10, 2020 (Edited Dec 10, 2020)
Assignment: "Data Science: Skills in Demand"
Faith Kane posted a new assignment: Data Science: Skills in Demand
Created Dec 10, 2020Dec 10, 2020
Material: "Data Science Fundamentals Images"
Faith Kane posted a new material: Data Science Fundamentals Images
Created Dec 9, 2020Dec 9, 2020
Material: "Data Science Fundamentals Resource Map"
Faith Kane posted a new material: Data Science Fundamentals Resource Map
Created Dec 8, 2020Dec 8, 2020
Assignment: "101 Exercises Prework Grade"
Ryan Orsinger posted a new assignment: 101 Exercises Prework Grade
Created Dec 8, 2020Dec 8, 2020
1 class comment
Assignment: "Data Science Community"
Faith Kane posted a new assignment: Data Science Community
Created Dec 8, 2020Dec 8, 2020
Material: "Day 1 Data Science Handout"
Ryan Orsinger posted a new material: Day 1 Data Science Handout
Created Dec 8, 2020Dec 8, 2020

Announcement: "Please join my class "Easley" on…"
Faith Kane via Quizizz
Created Dec 7, 2020Dec 7, 2020
Please join my class "Easley" on Quizizz using the link below.

Quizizz — Class Invite Link
https://quizizz.com/join?showGroupJoin=true&t=aca5554926f7c4c65854e373d8f07dcfdb16a51a5594bf1fd55d78e7ed3bf328e3e23c803f455502f5e9c07f7578660230126fe1e900561fd5c8675e851a84ac15c195445227e9f801406b8d43ec5cf3807d8dd975f54378cb5a09a21149ae4da197623d6a9ebeede91d8d5c21edc98c57336f85aa313c7079700a738bbe8369589ce54b0b4f3e4237ffcef49cb0bd7e&linktype=class-invite
- via Quizizz

Material: "Advice to Future Codeup Data Science Students"
Faith Kane posted a new material: Advice to Future Codeup Data Science Students
Created Dec 7, 2020Dec 7, 2020
Material: "Syllabus"
Ryan Orsinger posted a new material: Syllabus
Created Dec 7, 2020Dec 7, 2020
Material: "Model Evaluation Notes"
Maggie Giust posted a new material: Model Evaluation Notes
Created Nov 12, 2020Nov 12, 2020
Material: "Classification Evaluation Metrics Handout"
Maggie Giust posted a new material: Classification Evaluation Metrics Handout
Created Nov 12, 2020Nov 12, 2020
Material: "Classification Overview Handout"
Maggie Giust posted a new material: Classification Overview Handout
Created Nov 12, 2020Nov 12, 2020
Material: "Hypothesis Testing Handout"
Maggie Giust posted a new material: Hypothesis Testing Handout
Created Nov 12, 2020Nov 12, 2020
Material: "Probability Distributions Handout"
Maggie Giust posted a new material: Probability Distributions Handout
Created Nov 12, 2020Nov 12, 2020
Material: "Data Viz Resources"
Maggie Giust posted a new material: Data Viz Resources
Created Nov 12, 2020Nov 12, 2020
Material: "Data Science for Social Good"
Maggie Giust posted a new material: Data Science for Social Good
Created Nov 12, 2020Nov 12, 2020
Easley Data Science
Now We Know Game

I set a timer for 60 seconds.
In that time, you shout out something you know that you know.
Something that you've acquired..
My job is to type it down as fast as I can
See if you can state things you know faster than I can type
Collaborative 
As many participating as possible



Now I know:
- how to clone a repo in github
- select is from the db and from is the table
    - 
- my terminal workflow
- SQL joins
- default in order by is ascending
- how to use wildcard in SQL
- CRUD stands for create, read, update, delete
- how to use WHERE clauses
- basic select statements
- working with concat
- how to push your work as soon as you make updates
- create repositories
- how to create ignored files
- aggregate functions
    - functions that work on a list
    - count, average, min, max


## I think I've Got It, but I'm not too sure about ....
- actually creating tables in sql
    - we will be creating tables from queries (later)
        - we will create temporary tables
        - it's super easy to remove the temporary part and have a new table
    - The Table creation syntax/commands are what we see when we look at:
        - Table Info in Sequel Pro
        - When we run the Show Create Table Tablename command.
        - CREATE TABLE table_name (
                id INT UNSIGNED NOT NULL AUTO_INCREMENT,
                author_first_name VARCHAR(50),
                author_last_name  VARCHAR(100) NOT NULL,
                content TEXT NOT NULL,
                PRIMARY KEY (id)
        );
- distinct vs. group by
    - All distinct does is returns unique values (numbers, strings, dates, whatever)
```
use employees;

select distinct first_name
from employees;

# This query produces output that is identical to the above SELECT DISTINCT
# Group By Does 3 Things
# 1. The column we Group By works like selecting distinct
# 2. Group By sorts our disinct values by the column we group by
# Aggregate functions: count, average, median, min, max, standard deviation, etc..
select first_name
from employees
group by first_name;
```

- Any time we aggreate or group by a column, we're changing and redefininig our level of observation:
    - Level of observation == what each row means and signifies
    - So what does that mean?
        - Take the employees table. What is each row? What does each row represent in the world? One employee.
        - If we do select first_name, group by first name, what do the rows of the output represent?
            - We're redifining our observation, each row, is a unique first_name

```
# The group by redefines our observation to be first_names (not individuals)
# Because we grouped by first_name, we can run count(*) to show the number of duplicate first_names
select first_name, count(*)
from employees
group by first_name;

```

Aggregate functions like count, avg, min, max, average don't need group by to run. We can average a list of numbers all day. But, groupping by allows us to use our aggregate function(s) on each group.
```
# How many people work in each department?
# "How many" == English for "Count"
# "Each Department" == English for Group By dept_no
# Trick: The column we group by is the column that comes after our english "Each X"
# If I say I want count for each dept_no, then we group by dept_no.
# We get the aggregate for each group
select dept_no, count(dept_no)
from dept_emp
group by dept_no;
```


```
# Get the department with the highest range (max - min) salary
select dept_no, max(salary) - min(salary) as "salary_range"
from salaries
join dept_emp using (emp_no)
group by dept_no
order by salary_range DESC
LIMIT 1;
```


- if we have to use group by every time we use count - no.
    - short answer: no. We can just count stuff.
    - If we group by, however, we can count occurrences in each group.

- SQL troubleshooting (error messages or how to make a query)
    - Remember to put The error message + MySQL in ytour search.
    - "Googling the error message" should give you something to work with..
    - "Google the error message" sounds like great advice, unless the results don't make any sense.
    - Break things down.
    - do one part of the query at a time.
    - Start small - break the problem down and build your solution up
    - Usually, folks are trying to do too much at once...
- working with time in MySQL
    - we have date + time data types in MySQL
    - date, time, datetime
    - Be sure to put quotes around times so we're not doing math 2020-12-05 vs "2021-01-04"
    - stick with the YYYY-MM-DD format, wherever/whenever you can
- formatting queries (line breaks, syntax)
- select statements in select statements
    - these are a thing!
    - SubQueries help us solve multi-step problems
- the different kinds of joins
    - left, inner, right, and some other wacky ones
    - we'll use left and inner a bunch.
- knowing when to use WHERE and HAVING
    - WHERE is super powerful
- CASE statements
    - case statements are if/elses for SQL
    - covering them later this week!
- How to find Median
    - b/c MySQL, we'd have to calculate this using other MySQL arithmetic functions
    - realtalk - we'll "median" the heck out of our data.. in Pandas/python

now_we_know_content.md
Displaying now_we_know_content.md.