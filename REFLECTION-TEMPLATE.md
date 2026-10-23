# Caffeine Quest reflection

Name: Abraham Gonzalez

## Five questions before coding

1. Purpose: Sorting a list of items into ascending order using the Merge sort algorithm while keeping sability and the comparator call made with the sorting
2. Inputs and outputs: list<T> and comparator<Super T>, and sorted version of the original list and the long value representing total number of comparisons
3. Constraints: Must not use the java built in sorting, maintain stable sorting, operate in log time and use auxiliary space
4. Edge cases: empty lists, single element list, etc
5. Test oracle: the list is in correct sorted order, all original elements are there, the results match with the java's built in sort

## Explore Demo mode

Starting latitude/longitude:

| Filter | Rank | Store ID / name | Distance in miles |
|---|---:|---|---:|
| All stores | 1 | | |
| All stores | 2 | | |
| All stores | 3 | | |
| Drive-through only | 1 | | |
| Drive-through only | 2 | | |
| Drive-through only | 3 | | |

What changed, and why would alphabetical order not answer this search?

## Hand trace: merge [2, 7] and [3, 5]

| Step | Compared values (if any) | Item copied | Buffer so far |
|---|---|---|---|
| 1 |2vs3 |2 |[2] |
| 2 |7vs3 |3 |[2,3] |
| 3 |7vs6 |5 |[2, 3, 5] |
| 4 |none(right half empty) | 7 | [2, 3, 5, 7]

## Validation

Final SortCheck output or evidence filename: 

Additional test: input / expected output / actual output / reason:

Student-mode first three results for the two original searches:

How do they compare with Demo mode? Student map evidence filename:

## Investigate one feature (150-250 words)

Topic and class/method: CSV Parsing, from what I can understand, its a feature that read the data from the csv file and converts each row into a store object that can be searched, sorted and displayed on the map provided when we startup the program and the application loads the dataset

Short relevant code excerpt: 
String[] data = line.split(",");
String storeName = data[0].trim();
String city = data[1].trim();
double latitude = Double.parseDouble(data[2]);
double longitude = Double.parseDouble(data[3]);

Explanation and concrete example:CSV parsing is the process of reading a Comma-Separated Values (CSV) file and converting each row into data that the program can use, if the CSV contains a row representing a Starbucks location in Merced, the parser extracts the values from the row and creates a store record. That record is then added to a collection of stores used by the application

Source consulted (title and URL or course reference): Oracle Java Tutorials - Basic I/O and File Processing: https://docs.oracle.com/javase/tutorial/essential/io/

## Customization

Feature: NA

Files changed and explanation: NA

New-feature test and result: NA

Default-behavior regression check: NA

## Algorithm explanation

1. Time complexity and reasoning: Merge sort runs in O(n log n) time and the algorithm divides into two halves until each sublist has one element
2. Auxiliary space: it requires O(n) because it uses a buffer list that temporarily stores the merrged elements before the implementing the copies to the original list
3. Stability and how my code preserves it: its a stable algorithm because when two elements compare as equal, I just have to select the left half
4. Why Demo/Student comparison counts may differ: its because one is java's built in sorting, and mine is a custom merge sort and each one has different optimizations and parts that might differe and affect performance
5. Why a single short timing is insufficient: because it can be affected by processor load, memort useage and background apps

## Demonstration checklist

- [ ] Student search and map
- [ ] Explain one merge comparison
- [ ] Show customization
