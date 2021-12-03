# Abstract
FP-Growth is an algorithm for extracting frequent itemsets with applications in association rule learning that emerged as a popular alternative to the established Apriori algorighm

In general, the algorithm has been designed to operate on databases containing transactions, such as purchases by customers of a store. An itemset is considered as "frequent" if it meets a user-specified support threshold. For instance, if the support threshold is set to 0.5 (50%), a frequent itemset is defined as a set of items that occur together in at least 50% of all transactions in the database.

# Why not Apriori algorighm

1. Using Apriori needs a generation of candidate itemsets. These itemsets may be large in number if the itemset in the database is huge.
2. Apriori needs multiple scans of the database to check the support of each itemset generated and this leads to high costs.

These shortcomings can be overcome using the FP growth algorithm.

# How does FP Growth Algorithm Work

![](https://github.com/Pramodgopinathan/FB-Growth/blob/64f49fb3553cea03f3f28937377538c8df2c1c9d/Table%201.0.png)

Above table shows the list of transaction done 

Step 1 — Counting the occurrences of individual items
The first step of the FP Growth algorithm is to count the occurrences of individual items. The below table shows the counts of each item:

![](https://github.com/Pramodgopinathan/FB-Growth/blob/0f348423c5877f07bd4e66860b8a78cf6d303b63/Table%201.1.png)

Step 2— Filter out non-frequent items using minimum support
You need to decide on a value for the minimum support: every item or item set with fewer occurrences than the minimum support will be excluded.
In our example, let’s choose a minimum support of 7. This means that we are going to discard items Flour and Butter.



Step 3— Order the itemsets based on individual occurrences
For the remaining items, we will create an ordered table. This table will contain the items that have not been rejected yet, and the items inside a transaction will be ordered based on individual product occurrence.

![](https://github.com/Pramodgopinathan/FB-Growth/blob/31e203be06a3c3c6a3e97c2cc2623c8c363782fe/Table%201.2.png)

Step 4— Create the tree and add the transactions one by one
Now, we can create the tree starting with the first transaction. Each product is a node in the tree, as follows:

![](https://github.com/Pramodgopinathan/FB-Growth/blob/4d8bbf6fcc80b255e7bd1c05ff4acf6cc69ab417/Table%201.3.png)

Once this FP tree is constructed, it is much faster to traverse it and find information on the most frequent itemsets.


