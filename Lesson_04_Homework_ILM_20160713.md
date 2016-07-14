#Lesson 4 Homework: Command Line 

##Question 1
*Look at the head and the tail of chipotle.tsv in the data subdirectory of this repo. Think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)*
```
head -n100 chipotle.tsv
tail chipotle.tsv
```

1. tab separated values - a flat file of sequential orders.
2. each column:
   1. **order_id** order each row belongs to, a type of key if you think of the tsv file as a table
   2. **quantity** quantity of each component (item) in the order 
   3. **Item_name** name of item i.e. what is being ordered
   4. **Choice_description** sub category of item or extra descriptor of item, also customization, if any.
   5. **item_price** price of that item including any multiplier for quantity e.g. canned soda qty 1 = 1.09, another row with canned soda qty 2 = 2.18
3. each row is one item in an order. if only one item is ordered then it would be the whole order.

##Question 2
*How many orders do there appear to be?*

```
tail -n1 chipotle.tsv
```
There are **1834 orders total**

##Question 3
*How many lines are in this file?*
```
wc -l chipotle.tsv 
```
There are **4623 lines in the file.**

##Question 4
*Which burrito is more popular, steak or chicken?*
```
grep "Chicken Burrito" chipotle.tsv | wc -l
grep "Steak Burrito" chipotle.tsv | wc -l

grep "Chicken Burrito" chipotle.tsv | wc -l
     553
grep "Steak Burrito" chipotle.tsv | wc -l
     368
grep -E "2 Steak Burrito" chipotle.tsv | wc -l
      14
grep -E "2 Chicken Burrito" chipotle.tsv | wc -l
      28
grep -E "3 Chicken Burrito" chipotle.tsv | wc -l
       2
grep -E "3 Steak Burrito" chipotle.tsv | wc -l
       2
grep -E "4 Steak Burrito" chipotle.tsv | wc -l
       0
grep -E "4 Chicken Burrito" chipotle.tsv | wc -l
       2
grep -E "5 Chicken Burrito" chipotle.tsv | wc -l
       0
grep -E "5 Steak Burrito" chipotle.tsv | wc -l
       0
```

1. There are 553 lines containing "Chicken Burrito"
2. There are 368 lines containing "Steak Burrito"
3. it appears that chicken is more popular
4. Checking for some phenomenon where steak burritos are frequently ordered in multiples (qty 2 or greater) finds some rows that way but not enough to out strip chicken burritos which are ordered in multiples more often. (used tab literal in terminal ctrl-v then <tab> to match rows with quantities)
5. *Chicken burritos are more popular than steak burritos*

##Questions 5
*Do chicken burritos more often have black beans or pinto beans?*
```
grep -E "Chicken Burrito.*Black Beans" chipotle.tsv | wc -l
     282
grep -E "Chicken Burrito.*Pinto Beans" chipotle.tsv | wc -l
     105
```

1. 282 rows for chicken burritos with black beans
2. 105 rows for chicken burritos with pinto beans
3. 19 rows existed where two chicken burritos were ordered with black beans, and 2 rows existed where chicken burritos were ordered with pinto beans. Neither was ordered in a multiple of three
4. *black beans are more popular than pinto beans*

##Question 6
*Make a list of all of the CSV or TSV files in the our class repo. repo (using a single command). You will be working on your local repo on your laptop. Think about how wildcard characters can help you with this task.*
```
cd DS-SEA-3/
ls -R -a1 | grep \.[ct]sv$
```

1. Airline_on_time_west_coast.csv
1. NBA_players_2015.csv
1. airlines.csv
1. bank-additional.csv
1. bikeshare.csv
1. chipotle.tsv
1. citibike_feb2014.csv
1. drinks.csv
1. drones.csv
1. hitters.csv
1. icecream.csv
1. imdb_1000.csv
1. mtcars.csv
1. ozone.csv
1. rossmann.csv
1. rt_critics.csv
1. sms.tsv
1. stores.csv
1. syria.csv
1. time_series_train.csv
1. titanic.csv
1. ufo.csv
1. vehicles_test.csv
1. vehicles_train.csv
1. yelp.csv
1. 2015_station_data.csv
1. 2015_trip_data.csv
1. 2015_weather_data.csv

I chose to exclude a file that was a .csv.zip since that is really a zip file.

##Question 7 
*Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files of our class repo.*
```
cd DS-SEA-3/
grep -i -r "dictionary" . | wc -l
```
1. returns a row count of 85
2. assuming there are no duplicates of 'dictionary' on each row
3. **the final answer is 85**

##Question 8
*Optional: Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!*
```
cut -f3,4 chipotle.tsv | Sort | uniq | wc -l
```
1. Cut out the item and description columns from the original file
2. Sort all the rows alphabetically
3. only retain the unique rows
4. count all remaining rows
5. returns a count of 1872 (from 4623 in the original file)
6. There were 1872 distinct things ordered in the order data set.

----
