# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

![ASSIGNMENT](https://github.com/user-attachments/assets/abd87f41-80ff-4ddb-9086-3bc442088811)

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

![ASSIGNMENT](https://github.com/user-attachments/assets/abd87f41-80ff-4ddb-9086-3bc442088811)

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
The two possible designs for the Customer Address table:
1: One in which the previous ddress of the customer is Overwriteen by the new one.
        CUSTOMER_ADDRESS Table could be like this:
            CustomerID (PK, FK from Customer)
            Adress
            City
            PostalCode
            Country
2: One that keeps Changes of the addresses of the customer (history of the addresses)
			CUSTOMER_ADDRESS Table
			Customer_Adress_ID(PK)
            Customer_ID (PK, FK from Customer)
            Address
            City
            PostalCode
            Country
            Date_from (Date when the customer moved in an address)
            Date_to   (Date when the customer moved out of an address)




Privacy Implications:

   In contrary to type 2, type 1 only stores the latest address, thus limiting the amount of personal data retained, hence it is privacy-friendly.
   retaining a full address history could raise concerns about the long-term storage of sensitive information; therefore, proper data retention policies are necessary here to protect the privacy of the customer.


## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
```
Differences:

    Complexity
        The AdventureWorks schema is more complex and includes many more tables for various business functions. For example for the Sales function it contains 18 tables while in the ERD of the bookstore model I designed the Sales function contains two tables only.

    Product Management
        The bookstore model simplifies the handling of all product information (book title, genre, etc.) in a single Book table. AdventureWorks uses separate tables for such a purrpose. 

If I had time I would make many changes. For example, if the bookstore sells different types of products (e.g., books, stationery, etc.), it may be beneficial to split Books into multiple tables or add a Category table similar to AdventureWorks' product management. Currently, the bookstore model uses a Sales table to track which books were sold in an order. This could be further refined  include additional product-specific details like discounts or promotions.
# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `September 28, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-4-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
