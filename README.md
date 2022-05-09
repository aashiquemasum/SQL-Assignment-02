Database:
A database is an organized collection of structured information, or data, typically stored electronically in a computer system.

Tabe in database:
Tables are database objects that contain all the data in a database. In tables, data is logically organized in a row-and-column format similar to a spreadsheet. Each row represents a unique record, and each column represents a field in the record.

What are the components we need to connect to a database server:
Applies to: 
yesSQL Server (all supported versions) 
YesAzure SQL Database 
YesAzure SQL Managed Instance 
yesAzure Synapse Analytics 
yesAnalytics Platform System (PDW)

SQL Server Management Studio provides functionality for managing every component of SQL Server. Use Management Studioto connect to:

An instance of the SQL Server Database Engine.

Analysis Services.

Integration Services.

Reporting Services.

Although Management Studio allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection. Management Studioprovides the Connect to Server dialog box to configure connection properties to SQL Server components. When Management Studiostarts, it opens the Connect to Server dialog box and prompts you to connect to a server. The Connect to Server dialog box retains the connection settings from the last time it was used.


1. Write a query to get all data of actor.


elect * from actor


<img width="960" alt="sql2 1" src="https://user-images.githubusercontent.com/102998720/167485254-97a69899-dbf2-43ec-a1a5-f8224da8b9ca.png">



2. Write a query to get email and last name of customer.

SELECT email, last_name FROM customer


<img width="960" alt="psql2 2" src="https://user-images.githubusercontent.com/102998720/167485345-52b3801d-a9e2-40a0-a4b7-669573fdea86.png">



3.Write a query to get title, description and release year of film.

SELECT title, description, release_year FROM film

<img width="960" alt="psql2 3" src="https://user-images.githubusercontent.com/102998720/167485399-c0badf46-bd7c-4d5c-bfef-45cd189d52c3.png">



4. Query city and country id in the city table.

SELECT city, country_id FROM citySELECT city, country_id FROM city


<img width="960" alt="psql2 4" src="https://user-images.githubusercontent.com/102998720/167485441-8cf1d575-a849-4eba-a6b1-bef627d4848b.png">



5. Write a query to get amount, payment date and customer id from customer table.
 
SELECT customer_id FROM customer( amount and payment date dose not exit)


<img width="960" alt="psql2 5" src="https://user-images.githubusercontent.com/102998720/167485509-e8a13343-266e-4d01-a3d7-4de6f8667729.png">



6. Write a query to get all data of language.

SELECT * FROM language


<img width="960" alt="sql2 6" src="https://user-images.githubusercontent.com/102998720/167485576-1fe9959d-0181-426a-931d-ba429dc2de46.png">



7. Query all columns for a payment in payment table with customer id 10.

SELECT * FROM payment WHERE customer_id= 10


<img width="960" alt="sql2 7" src="https://user-images.githubusercontent.com/102998720/167485686-bddb0748-caf9-440c-a201-11e69c986256.png">


8. Query last name and first name of customers in customer table whose first names are "Mary"

SELECT last_name, first_name FROM customer WHERE first_name= 'Mary'


<img width="960" alt="sql2 8" src="https://user-images.githubusercontent.com/102998720/167485715-bd99cd81-0543-4f23-8578-a7f841c64fe8.png">



9. Query last name and first name of customers in customer table whose first names are "Mary" and last names are "Smith".
    
SELECT last_name, first_name FROM customer WHERE first_name= 'Mary' and last_name= 'Smith'

<img width="960" alt="sql2 9" src="https://user-images.githubusercontent.com/102998720/167485768-2bc6c6b5-e7a4-4607-8c11-8c23e3c538be.png">



10. Query last name and first name of customers in customer table whose first names are "Susan" or last names are "Jones".
 
   SELECT last_name, first_name FROM customer WHERE first_name='Susan' or last_name='Jones'
   
   
   <img width="960" alt="sql2 10" src="https://user-images.githubusercontent.com/102998720/167485854-192467d6-8aec-4d08-ad71-87e9ef41663d.png">

   

11. Query email of customers in customer table whose first name is "Mar", "Mary" or "Mari".
    
SELECT email FROM customer WHERE first_name='Mar' or first_name='Mary' or first_name='Mari'


<img width="960" alt="sql2 11" src="https://user-images.githubusercontent.com/102998720/167485911-427509ca-414a-4a60-9b17-4909baa68393.png">



12. Query last name and first name of customers in customer table whose first names start with "Ma".

SELECT last_name, first_name FROM customer WHERE first_name like 'Ma%'


<img width="960" alt="sql2 12" src="https://user-images.githubusercontent.com/102998720/167485972-40a4c489-af97-46f6-b1f9-b32c90e73fdf.png">


13. Write a query to get staff id, first name and username of staff in staff table whose staff id is 10.

SELECT staff_id, first_name, username FROM staff WHERE staff_id=10



<img width="960" alt="sql2 13" src="https://user-images.githubusercontent.com/102998720/167486005-887891fb-5e5c-4788-b57b-46653b9c291d.png">


(There is no staff id 10 exist)



14. Query last name and first name of customers in customer table whose first name start with letter "M" and contains 3 to 5 characters.

SELECT last_name, first_name FROM customer WHERE first_name LIKE 'M%' AND LENGTH(First_name) >=3 AND LENGTH(first_name) <=5

<img width="960" alt="psql2 14" src="https://user-images.githubusercontent.com/102998720/167486097-fa1a3873-276d-45a0-b27d-53b2393437b8.png">



15. Query last name and first name of customers in customer table whose first names start with "Bra" and last names are not "Motley".

SELECT last_name, first_name FROM customer WHERE first_name LIKE '%Bra%' AND last_name NOT LIKE 'Motley'

<img width="960" alt="sql2 15" src="https://user-images.githubusercontent.com/102998720/167486154-231cbaa8-77b8-4dc7-be27-293985778c2a.png">



16. Query store id of stores that have more than 300 customers in customer table.
   
SELECT Store_id FROM customer GROUP BY store_id HAVING COUNT(customer) > 300


<img width="960" alt="sql2 16" src="https://user-images.githubusercontent.com/102998720/167486209-851ea030-b4a1-48f3-a3ec-23d58d47e36e.png">


17. Write a query to select all details of the only customers who have been spending more than 200 in customer table.
    
SELECT * FROM customer GROUP BY customer.customer_id HAVING SUM(amount) > 200


<img width="960" alt="sql2 17" src="https://user-images.githubusercontent.com/102998720/167486249-9e6000f4-0be9-4ef2-aa5a-595bed37a0c8.png">


(ERROR:  column "amount" does not exist)

18. Query all columns in film table where the film_id is less than 4.
    
SELECT * FROM film WHERE film_id < 4


<img width="960" alt="sql2 18" src="https://user-images.githubusercontent.com/102998720/167486286-aee6c81c-8e11-4982-8bdc-8a18fa727f87.png">


19. Write a query to get all data from address table.
    
SELECT * FROM address


<img width="960" alt="sql2 19" src="https://user-images.githubusercontent.com/102998720/167486326-247c3621-af71-47c5-a9b8-079250accbb9.png">


20. Query rental date, customer id and rental id in rental table when rental date is 2005-05-25.
    
SELECT rental_date, customer_id, rental_id FROM rental WHERE rental_date='%2005-05-25'

<img width="960" alt="sql2 20" src="https://user-images.githubusercontent.com/102998720/167486401-325a835d-b0dd-4a15-ba72-f5759c38634b.png">



21. Query all columns for customers in customer table with store id 2 or customer id 7.
   
SELECT * FROM customer WHERE STORE_ID='2' OR CUSTOMER_ID='7'


<img width="960" alt="sql2 21" src="https://user-images.githubusercontent.com/102998720/167486431-f260f777-17e8-4ab7-b65f-452d211be3fb.png">


 22. Query all columns for customers in customer table who have spent amount more than $200.
   
 SELECT * FROM customer WHERE amount > '200'


<img width="960" alt="sql2 22" src="https://user-images.githubusercontent.com/102998720/167486495-9d7ae7fb-4291-4dd0-9b84-fb4ab78f8699.png">



 23. Query amount and payment_date from payment where the amount paid was less than $2.
    
SELECT amount, payment_date from payment WHERE amount<2


<img width="960" alt="sql2 23" src="https://user-images.githubusercontent.com/102998720/167486538-6956e652-c273-4def-a549-5f98c340bbf2.png">



24. Write a query to get a list of actors with the first name Chris, Cameron, or Cuba.
   
 SELECT DISTINCT * FROM actor WHERE first_name = 'Chris' OR first_name= 'Cameron' OR first_name='Cuba'


<img width="960" alt="qsl2 24" src="https://user-images.githubusercontent.com/102998720/167486587-afcddc42-b293-41a0-bfec-fe6261e24488.png">



 25. Query last name of customers in customer table whose first names are "John".
    
SELECT last_name FROM customer WHERE first_name = 'John'




<img width="960" alt="sql2 25" src="https://user-images.githubusercontent.com/102998720/167486633-6a1f676a-8a82-480e-81a0-9392d58d549a.png">



26. Write a query to get staff id, first name and username of staff in staff table whose store id is less than 6.
   
 SELECT staff_id, first_name, username FROM staff WHERE store_id < 6
 
 
 
 <img width="960" alt="sql2 26" src="https://user-images.githubusercontent.com/102998720/167486659-32b8c945-2e44-41e4-95fc-2ad5722092fe.png">

 

 27. Write a query to get release year, rental duration and rental rate of films in film table.
    
SELECT release_year, rental_duration, rental_rate FROM film




<img width="960" alt="sql2 27" src="https://user-images.githubusercontent.com/102998720/167486704-4030bb97-a05b-4724-ba7a-3148e024cbae.png">



28. Write a query to get city id and country id of country in country table whose name is "New York".
    
 SELECT CITY_id, country_id FROM country WHERE city= 'New York'


<img width="960" alt="sql2 28" src="https://user-images.githubusercontent.com/102998720/167486738-6473e24c-a26f-4aad-9bc6-b1c10eb0657b.png">



29. Write a query to get all data of city table.

SELECT * from city
    
    <img width="960" alt="sql2 29" src="https://user-images.githubusercontent.com/102998720/167486786-d70d1216-47d9-47c5-911c-8a439ab5b303.png">

    
    
30. Write a query to get film id of film in film_category table with category_id 2.

SELECT film_id from film_category WHERE category_id=2


<img width="960" alt="sql2 30" src="https://user-images.githubusercontent.com/102998720/167486822-376203c4-29a5-45ee-b7e2-13389554c3a5.png">

