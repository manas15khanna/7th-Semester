# Filtering Streams
1. Continuous Data enters the system 
2. Filtering rule is applied
3. Useful Data is selected
4. Unwanted Data is Discarded 
5. Selected Data is Analyzed 
# Counting Distinct Elements in a Stream 
- Distinct Elements are unique items that appear only once in a dataset
- Even if an item appears many times, it is counted only once
- These are unique values without duplication 
- Ex: A,B,C,D,A,E,F,A 
	- Distinct: A,B,C,D,E,F
		- => 6
- A data stream continuously generates data, counting distinct elements means finding how many unique items have appeared in a stream. 
- Instead of counting every record, we often need to know how many unique items exist. 
## Steps
1. Receive continuous data stream 
2. Check whether each element has already appeared 
3. If it is new, add it to the list of unique elements 
4. Otherwise, discard the elements
# Decaying Windows and Link Analysis
