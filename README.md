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

