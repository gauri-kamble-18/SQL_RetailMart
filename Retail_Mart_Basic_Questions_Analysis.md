SQL ASSIGNMENT

RETAIL MART

BASIC ASSIGNMENT QUESTIONS

1)Select all campaigns that are currently active.

SELECT \*  
FROM tbl\_campaign  
WHERE CURDATE() BETWEEN start\_date AND end\_date;

**Actionable Insight:** Monitor the performance of current campaigns to assess their effectiveness.

**Future Step:** Allocate additional resources or adjust strategies for underperforming campaigns based on performance metrics.

2)Select all customers who joined after January 1, 2023\.

SELECT \*  
FROM tbl\_customers  
WHERE join\_date \> '2023-01-01';

**Actionable Insight:** New customers may require onboarding or targeted marketing to increase engagement.

**Future Step:** Develop a welcome campaign or special offers to encourage first-time purchases and build loyalty among new customers.

3)Select the total amount spent by each customer, ordered by amount in descending order.

SELECT total\_spent FROM tbl\_customers ORDER BY total\_spent DESC;

**Actionable Insight:** Identify high-spending customers to target them with premium offers and loyalty rewards.

**Future Step:** Create personalized marketing strategies for top customers, including exclusive promotions or VIP events.

4)Select the products with a price greater than $50.

SELECT product\_id,product\_name FROM tbl\_products WHERE price \> 50;

**Actionable Insight:** High-priced products can be targeted for special promotions or marketing campaigns.

**Future Step:** Consider bundling these products with lower-priced items to encourage higher-value purchases.

5)Select the number of orders placed in the last 30 days.

SELECT COUNT(\*) FROM tbl\_orders WHERE order\_date \>= CURDATE() \- INTERVAL 30 DAY;  
SELECT COUNT(\*) AS number\_of\_orders  
FROM tbl\_orders  
WHERE order\_date \>= CURDATE() \+ INTERVAL 30 DAY;

**Actionable Insight:** A surge in recent orders indicates effective marketing or seasonal demand.

**Future Step:** Analyze the causes of this trend and replicate successful tactics in future campaigns or peak seasons.

6)Order the products by price in ascending order and limit the results to the top 5 most affordable products.

SELECT price FROM tbl\_products ORDER BY price ASC LIMIT 5;

**Actionable Insight:** Promote low-cost items to attract budget-conscious customers.

**Future Step:** Implement promotional campaigns highlighting these products during sales events or holiday seasons.

7)Select the campaign names and their budgets.

SELECT campaign\_name,budget FROM tbl\_campaign;

**Actionable Insight:** Evaluate budget distribution across campaigns to identify potential inefficiencies.

**Future Step:** Reallocate budgets based on campaign performance and ROI analysis to optimize marketing spend.

8)Select the total quantity sold for each product, ordered by quantity sold in descending order.

SELECT oi.product\_id, SUM(oi.quantity) AS total\_quantity\_sold  
FROM tbl\_order\_items oi  
JOIN tbl\_orders o ON oi.order\_id \= o.order\_id  
GROUP BY oi.product\_id  
ORDER BY total\_quantity\_sold DESC;

**Actionable Insight:** Identify best-selling products to ensure adequate inventory and avoid stockouts.

**Future Step:** Increase marketing efforts for high-selling products and consider expanding their availability in more regions.

9)Select the details of orders that have a total amount greater than $100.

SELECT \* FROM tbl\_orders WHERE total\_amount \> 100;

**Actionable Insight:** Understanding the characteristics of high-value orders can help tailor promotions.

**Future Step:** Create targeted marketing strategies that encourage upselling or cross-selling of products frequently included in high-value orders.

10)Find the total number of customers who have made at least one purchase.

SELECT COUNT(DISTINCT c.customer\_id) AS total\_customers\_with\_purchases  
FROM tbl\_customers c  
JOIN tbl\_orders o ON c.customer\_id \= o.customer\_id;

**Actionable Insight:** Knowing the number of engaged customers can guide retention efforts.

**Future Step:** Implement targeted re-engagement campaigns for customers who have not purchased recently to encourage repeat sales.

11)Select the top 3 campaigns with the highest budgets.

SELECT campaign\_id, campaign\_name FROM tbl\_campaign ORDER BY budget DESC LIMIT 3;

**Actionable Insight:** Analyze the success of high-budget campaigns to determine effective marketing strategies.

**Future Step:** Invest more in successful campaigns while revisiting and refining less effective ones.

12)Select the top 5 customers with the highest total amount spent.

SELECT customer\_id, name FROM tbl\_customers ORDER BY total\_spent DESC LIMIT 5;

**Actionable Insight:** Focus on nurturing relationships with top customers to enhance loyalty and retention.

**Future Step:** Develop loyalty programs or exclusive offers for these customers to encourage continued spending and brand advocacy.

