## 1. Write an API endpoint 
Using any framework (Symfony, Laravel, Slim, Lumen, etc.) write an endpoint which accepts a POST request with the following parameters: 
- client_id (UUIDv4, required)
- email (string, required)
- phone number (string, optional)
- name (string, required)
- comment (string, required, max length: 1000 characters)

The endpoint should return a JSON response with proper status code.

Comment should be stored in a database. The database structure should be designed by you.\
Make a proper validation of input data. Add tests when you find them useful. \
Put the code in github (or other git repository) and send us the link.

## (For the purpose of testing Full Stack Developer skills): 
On the project we are using React library with Redux Toolkit Query (RTKQ) for fetching data from the API and managing the state.
To make a picture more full: 
- create a simple React app with RTKQ
- create CRUD based on task #1 using RTKQ
- add a simple UI to the app which will include: 
  - a form to create a new entity with all the fields from the task #1
  - a list of all entities with the possibility to delete an entity
  - a form to update an entity
  - delete entity button
- On the project for validation we are using Formik (but not necessary, any form state management will be ok)
- On the project for styling we are using Material UI (prefer to use it to create very simple UI of lists, forms, 
  buttons etc.)

## 2. Check the pull request
   You have a Pull Request to review! \
   Documentation states the following:
   - ENDPOINT: https://api.nordiceasy.no/register METHOD: POST
   - PARAMS:
     - client_id: aabbcc
     - email: your@email.address
     - name: Your Name

   RETURNS:
   - sl_token: This token string should be used in the subsequent query. Please note that this token will only last 1 hour
   from when the REGISTER call happens. You will need to register and fetch a new token when you need it.
   - client_id: returned for informational purposes only
   - email: returned for informational purposes only
   
   You receive a pull request with the following line of code. Please review the code.

```<?php 
$tokenInfo = file_get_contents('https://api.nordiceasy.no/register?client_id=aabbcc&email=my@name.com&name=My%20Name'); 
```

## 3. Legacy code refactoring
   Refactor the following piece of legacy code\
   You do not need to write code, you may instead describe all the problems you see and how you would refactor this
   legacy piece of code. Bonus for thinking in an object-oriented way. Of course you may also submit stubs of the code
   refactored if you have time.

* Please note this is not at all code taken from Nordic Easy.

```<?php 
if ($_REQUEST['email']) {
    $masterEmail = $_REQUEST['email']; 
}

$masterEmail = isset($masterEmail) && $masterEmail ? $masterEmail 
: array_key_exists('masterEmail', $_REQUEST) && $_REQUEST["masterEmail"] ? $_REQUEST['masterEmail'] : 'unknown'; 

echo 'The master email is ' . $masterEmail . '\n'; 
$conn = mysqli_connect('localhost', 'root', 'sldjfpoweifns', 'my_database');
$res = mysqli_query($conn, "SELECT * FROM users WHERE email='" . $masterEmail . "'"); $row = mysqli_fetch_row($res); 
echo $row['username'] . "\n";
```

## 4. Open source libraries
Would you use a class/library provided by an external framework in your code, why or why not? 

