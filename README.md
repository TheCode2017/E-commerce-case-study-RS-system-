# E-commerce-case-study-RS-system
Implemented a recommendation engine for an e-commerce company.

This is a case study where I built a recommendation for an e-commerce company. The case study is as follows:

# Case 1: How can we determine what product brands matter?
What brands matter to customers? When do they matter? To whom? How do we know?
In this case we want to focus on Adhesives & Sealants. Now, like most industrial supplies,
Adhesives and Sealants are not a category of products that is well codified. It’s a bit open to
interpretation, so don’t worry too much about specific boundaries. Focus more on using the
data that you have (publicly) available to you that enables you to determine audience, brands
and situations, etc. The output should represent your survey into this category. What
information can you share to help us gain insight?
We’ve included some competitor links to help you out.
You goal is to show us how you would be able to:
• Identify substitute items
• Identify instances of people purchasing more expensive substitute
o These are brands that people care about
o Who are these people?
o When and why do these brands matter?


# Case 2: How can we find reasonable complements?
We’ve all seen Amazon or other sites show related products through the lens of “customers
who viewed also viewed” or “customers who purchased also purchased”. These techniques
have their virtues and inefficiencies.
You goal is to:
• Show E-Corp how it should think about complements
• Identify related products can we detect and show how we would detect them
automatically for our ecomm business
As in the previous exercise we’re going to focus on Adhesives & Sealants. It’s a small category
that interacts with many other industrial products frequently. To that end we’ve given you two
data sets, both of which have been sanitized.
• The first includes all transactions that contain an A&S product across a six-month time
frame.
• The second includes all transactions across a two-week period. We have selected the
smaller period to make the data set more manageable.
You don’t necessarily need both data sets, but we wanted to be thorough. We’ve provided a
data dictionary below to help you make sense of the data provided. Should you have any
additional questions about the data, feel free to email us.


Data dictionary:
Column title Description
order_number Number associated with a purchase (sanitized)
l1 Level 1 Product hierarchy (most broad)
l2 Level 2 Product hierarchy
l3 Level 3 Product hierarchy (most granular)
sku Product ID (sanitized)
brand Product brand (sanitized)


Approach:

Step 1-Data Exploration

-The dataset consists of 2107537 rows(observations) 6 columns(variables). 
-Used pandas_profiling package to get a detailed description about each column,the sparsity percentage in the dataset and the correlation between the columns. 
-Identified the brands that was bought the most.
-Identified the items that were bought the most as identified by the sku(stock keeping unit) column.

Step 2-Data Preprocessing

-To avoid the user cold start problem in Rec engines we will take into account only the users who have made more than a threshold number of orders.(For this dataset I have taken users who have made more than 10 transactions).
- One Hot Encoding the 'l3' column(the most granular column) makes the unique items in 'l3' as separate columns.(helpful in creating the item matrix which we will see later).
-Remove all the unnecessary columns,we will take into account the order_id and the'l3' columns that we encoded only.
- Consolidate each row(order) into a single record such that order_id column is sorted.Also reset the index.
-Split the columns into user and item columns in order to construct the user-item matrix.User column='order_id',item_columns=remaining columns.

Step 3- Building the Recommendation system

*Creating the similarity matrix with rows and columns as item_columns. An item-item matrix(Item-based collaborative filtering).
*Inserting values into the similarity matrix.Use Jaccard similarity to compute the similarity between items(Jaccard similarity=|intersection(x,y)|/|union(x,y)|. Fill in the diagonal values with similarity of 1.0,can reduce the time complexity of filling in the matrix by noting the fact that the similarity matrix is symmetric.
*Create the score matrix for each user by taking the dot product of the data matrix with the similarity matrix.
*Generate the top n recommendations for each user.Each user corresponds to a unique order_id.
*Sort the items by user_column in descending order of the score value.

The code and outputs are uploaded in separate files.





