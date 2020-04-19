# MongoDB | CRUD Operations


<br>

![](https://media.giphy.com/media/sRFEa8lbeC7zbcIZZR/giphy.gif)


<br>



## MongoDB CRUD Recap - Exercise



<br>



In case that you decided to experiment during the lecture and have dropped your previous database that included the collection of `employees`,  follow the *Task 1* and *Task 2* steps below to create a new database with the `employees` collection and populate it again with documents.

------


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

**Copy** the below code and run it in the `mongo` shell to insert the new documents representing our employees:

```js
db.employees.insertMany(
  [
    {
  name: "Sue",
  age: 19,
  phone: {
    personal: "555-123-123",
    work: "555-456-456",
    ext: "2342"
      },
  privileges: "user",
  favorites: { artist: "Picasso", food: "pizza"
      },
  finished: [
        17,
        3
      ],
  badges: [
        "blue",
        "black"
      ],
  points: [
        { points: 85, bonus: 20
        },
        { points: 85, bonus: 10
        }
      ]
    },
    {
  name: "Steve",
  age: 46,
  phone: {
    personal: "929-884-8752",
    work: "555-456-456",
    ext: "1109"
      },
  privileges: "admin",
  favorites: { artist: "Rembrandt", food: "kroketten"
      },
  finished: [
        25
      ],
  badges: [
        "red",
        "blue"
      ],
  points: [
        { points: 12, bonus: 5
        },
        { points: 40, bonus: 0
        }
      ]
    },
    {
  name: "Bob",
  age: 42,
  phone: {
    personal: "555-123-123",
    work: "555-456-456",
    ext: "7673"
      },
  privileges: "admin",
  favorites: { artist: "Miro", food: "meringue"
      },
  finished: [
        11,
        25
      ],
  badges: [
        "green"
      ],
  points: [
        { points: 85, bonus: 20
        },
        { points: 64, bonus: 12
        }
      ]
    },
    {
  name: "Willy",
  age: 22,
  phone: {
    personal: "555-123-123",
    work: "555-456-456",
    ext: "8263"
      },
  privileges: "user",
  favorites: { artist: "Cassatt", food: "cake"
      },
  finished: [
        6
      ],
  badges: [
        "blue",
        "Picasso"
      ],
  points: [
        { points: 81, bonus: 8
        },
        { points: 55, bonus: 20
        }
      ]
    },
    {
  name: "John",
  age: 34,
  phone: {
    personal: "555-123-123",
    work: "555-456-456",
    ext: "2143"
      },
  privileges: "admin",
  favorites: { artist: "Chagall", food: "chocolate"
      },
  finished: [
        5,
        11
      ],
  badges: [
        "Picasso",
        "black"
      ],
  points: [
        { points: 53, bonus: 15
        },
        { points: 51, bonus: 15
        }
      ]
    },
    {
  name: "Steve",
  age: 23,
  phone: {
    personal: "555-123-123",
    work: "555-456-456",
    ext: "8253"
      },
  privileges: "user",
  favorites: { artist: "Noguchi", food: "nougat"
      },
  finished: [
        14,
        6
      ],
  badges: [
        "orange"
      ],
  points: [
        { points: 71, bonus: 20
        }
      ]
    },
    {
  name: "Martin",
  age: 43,
  phone: {
    personal: "555-123-123",
    work: "555-456-456",
    ext: "5623"
      },
  privileges: "user",
  favorites: { food: "pizza", artist: "Picasso"
      },
  finished: [
        18,
        12
      ],
  badges: [
        "black",
        "blue"
      ],
  points: [
        { points: 78, bonus: 8
        },
        { points: 57, bonus: 7
        }
      ]
    }
  ]
)
```


<br>

<hr>

## ***

Once you have inserted the above documents in the collection `employees` using  your `mongo` shell,  perform the following queries:



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

<hr>

<br>

<details>
  <summary>Troubleshooting</summary>
  <p>If unable to execute Task 2, inserting the documents using `insertMany`, do the following steps: </p>
  <br>
  <ol>
    <li>On your system, navigate to the desired directory and save the file `employees.json` provided below.</li>
    <li>Open the terminal and navigate to the same directory of the `employees.json` file that you just saved.</li>
    <li>Run the below command <em>in the terminal</em> (<b>not mongo shell</b>) to import the documents in to the database from the json file:</li>
    <pre>mongoimport --db=my-first-db --collection=employees --file=employees.json --jsonArray</pre>
  </ol>
</details>
