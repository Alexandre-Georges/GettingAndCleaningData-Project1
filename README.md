# GettingAndCleaningData-Project1

## Disclaimer

As written in a forum thread, the inertial data folders should not be read.
https://class.coursera.org/getdata-012/forum/thread?thread_id=9

## Libraries used

* LaF: useful to read large fixed width files quickly, read.fwf is too slow
* ffbase: converts the object generated by LaF to a standard data frame
* plyr and dplyr: used to append a data frame to another and for the group by


## Script

The script uses 2 functions:
* loadData reads the different files, merges and joins them together in one nice and tidy data frame
* featureAvg calculates the average value of each column

Finally the result is written in a text file ready to be exported!


#### loadData

This function reads files in the fastest way, the feature datasets are pretty large so a library optimized for large file is used (LaF).

Column names are extracted from the features.txt files and added to the feature dataset as column names.
Note: Parentheses have been removed, otherwise R replaces them by periods which is frankly ugly.

Subject IDs and activity IDs are added as new columns to the feature dataset. That way we can know which activity and subject is associated with the row (set of measurements).

Then, columns are filtered to only keep mean and std for every measurement (cf codebook for more details) along with the subject and activity.


#### featureAvg

Once the dataset is tidy and contains only the required variables, we need to sort it.
To do that, the data set is grouped by activity and subject.

Then the function gets the average value of every column.


## Need more info?

The code is properly commented line by line and was made in the most self explanatory way.