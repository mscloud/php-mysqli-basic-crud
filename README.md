# ABOUT THE REPO
* Beginners reference on how to connect to a MySQL database using the MySQLi extension.
* Class based Database connection
* Added a simple query builder that accepts SQL Queries
* Includes a very basic CRUD operation
* Added method chaining
---
## Todos
- [ ] Add more query builders
  - [x] Select
  - [x] Where
  - [x] From
  - [x] Execute query
  - [x] Limit
  - [ ] Delete
  - [ ] Update
  - [ ] Join
- [x] Method Chaining
- [ ] Make use of AJAX for the CRUD part
- [ ] Integrate simple pagination plugin using vanilla js or jquery
- [ ] UI modification
- [ ] Integration of task runners or builders for css/js minifications
- [ ] More query builders for iterating result sets, etc.
- [ ] Login with session
- [ ] Namespaces
- [ ] Autoloading classes using composer
- [ ] Implementation of Model View Controller pattern
---

## Method Chaining

  Example of method chaining:
  
  **Include and Instantiate Database Class first**
  
  require_once('Database.php');
  
  $db = new Database();
  
  ### Returning all fields
  $result = $db->select()->from('user')->result(); //  return all fields from user table
  
  ### Specifying fields
  $result = $db->select('id, name')->from('user')->result(); // returns selected fields from user table
  
  ### Using where clause
  $id = 1;
  
  $result = $db->select()->from('user)->where('id = '.$id.'')->result(); // returns a user with an id of 1
  
  ### Limiting results
  $result = $db->select()->from('user')->limit(10)->result(); // returns 10 results only

  ### Looping results
  while($obj = $result->fetch_object()) {
    
    $obj->name;
    $obj->id;
    
  }
  
  
  ### Using raw queries
  $result = $db->query("SELECT * FROM user"); // just use the query()

   while($obj = $result->fetch_object()) {
    
    $obj->name;
    $obj->id;
    
  }
  
  
  



**_Note:_** _For more feature requests please open up an issue._
