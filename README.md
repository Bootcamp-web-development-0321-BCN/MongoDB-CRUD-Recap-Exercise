# MongoDB | CRUD Operations


<br>

![](https://media.giphy.com/media/sRFEa8lbeC7zbcIZZR/giphy.gif)


<br>



## MongoDB CRUD Recap - Exercise



<br>



### Getting Started

First, clone this repository as you will use it to import the data from the file`employees.json` to your MongoDB database.



```bash
git clone https://github.com/Bootcamp-web-development-0321-BCN/MongoDB-CRUD-Recap-Exercise.git

cd MongoDB-CRUD-Recap-Exercise
```




<br>



## Reference:



### [MongoDB - Collection Methods](https://docs.mongodb.com/v3.2/reference/method/#collection)

### [MongoDB - Query selectors](https://docs.mongodb.com/v3.2/reference/operator/query/#query-selectors)

### [MongoDB - `sort()`](https://docs.mongodb.com/v3.2/reference/method/cursor.sort/#cursor-sort)

------


<br>



**Task 1 :**



Run the below commands in `mongo` shell to:

- create a new database named `ironhack-inc`.

- check what is the name of the current database.

- list all of the collections of the current database.

     &

- **create a new collection** named `employees` in that database.

```js

use ironhack-inc


db.getName()


show collections


db.createCollection("employees");

```

<br>

<hr>

<br>



**Task 2 :** 

On your system, using the terminal navigate to the directory of the cloned repository containing the file `employees.json`.


Run the below command **in the terminal** (*not mongo shell*) to import the documents in to the database from the json file:

```bash
mongoimport --db=ironhack-inc --collection=employees --file=employees.json --jsonArray
```



<br>

<hr>

## ***



<br>



### Query the database





Once you have inserted the above documents in the collection `employees`  use your `mongo` shell to perform the following queries:



<br>


- **Task 3**: Find all employees that are over `30` years old.



<br>



- **Task 4:** Find all employees whose `age` is less than or equal to `30`.



<br>



- **Task 5:** Find all the employees whose favorite food is `pizza`.



<br>



- **Task 6:** Change `Willy`’s personal phone number to `"93-123-45-67"`.



<br>



- **Task 7:** Change Bob’s privilege to normal `"user"`.



<br>



- **Task 8:** Find all employees whose favorite artist is  `"Picasso"`.



<br>



- **Task 9:** Delete the employee whose name is `"John"`.



<br>



- **Task 10:** List all employees and [sort](https://docs.mongodb.com/v3.2/reference/method/cursor.sort/#cursor-sort) them by `name` appending to the end of the query the method [`sort`](https://docs.mongodb.com/v3.2/reference/method/cursor.sort/#cursor-sort)  like this: `.sort({name: 1})`  or   `.sort({name: -1})`  .



<br>




- **(EXTRA)** : Add a bonus of 15 to all those employees who have a bonus that is less than 10.



<br>

